<template>
    <base-dialog v-if="inputIsInvalid" title="Invalid input">
    <template #default>
        <p>At least one input value is invalid</p>
        <p>Please make sure you enter at least a few characters into each input field</p>
    </template>
    <template #actions>
        <base-button @click="inputIsInvalid=false"> Okay</base-button>
        
    </template>
</base-dialog>
  <base-card>
    <form @submit.prevent="submitData">
      <div class="form-control">
        <label> Title </label>
        <input type="text" id="title" name="title" ref="title" />
      </div>
      <div class="form-control">
        <label> Desciption </label>
        <textarea
          type="text"
          id="description"
          name="description"
          rows="4"
          ref="description"
        />
      </div>
      <div class="form-control">
        <label> Link </label>
        <input
          type="url"
          id="link"
          name="link"
          v-model="this.link"
          ref="link"
        />
      </div>
      <div>
        <base-button type="submit" @click="submitData"
          >Add Resourse</base-button
        >
      </div>
    </form>
  </base-card>
</template>


<style scoped>
label {
  font-weight: bold;
  display: block;
  margin-bottom: 0.5rem;
}

input,
textarea {
  display: block;
  width: 100%;
  font: inherit;
  padding: 0.15rem;
  border: 1px solid #ccc;
}

input:focus,
textarea:focus {
  outline: none;
  border-color: #3a0061;
  background-color: #f7ebff;
}

.form-control {
  margin: 1rem 0;
}
</style>

<style scoped>
div {
  background-color: #ffffff;
}
h2 {
  color: rgb(0, 0, 0);
}
</style>

<script>
export default {
  inject: ["addResourse"],
  data(){
    return{
        inputIsInvalid: false
    }
  },
  methods: {
    submitData() {
      const enteredTitle = this.$refs.title.value;
      const enteredDescription = this.$refs.description.value;
      const enteredLink = this.$refs.link.value;
      if(enteredTitle.trim()==='' || enteredDescription.trim()==='' || enteredLink.trim()===''){
        this.inputIsInvalid=true;
        return;
      }
      this.addResourse(enteredTitle, enteredDescription, enteredLink);
    },
  },
};
</script>