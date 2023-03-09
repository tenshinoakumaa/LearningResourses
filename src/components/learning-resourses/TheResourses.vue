<template>
  <base-card>
    <base-button @click="setSelectedTab('stored-resourses')" 
    :mode="selectedTab==='stored-resourses' ? null : 'flat'"
      >Stored resourses</base-button
    >
    <base-button @click="setSelectedTab('add-resourse')" :mode="selectedTab==='stored-resourses' ? 'flat' : null"
      >Add resourse</base-button
    >
  </base-card>
  <component :is="selectedTab"></component>
</template>

<script>
import StoredResourses from "./StoredResourses.vue";
import AddResourse from "./AddResourse.vue";

export default {
  components: {
    AddResourse,
    StoredResourses,
  },
  data() {
    return {
      selectedTab: "stored-resourses",
      storedResourses: [
        {
          id: "official-guide",
          title: "Official Guide",
          desciption: "The official VueJS documentation",
          link: "https://vuejs.org",
        },
        {
          id: "google",
          title: "Google",
          desciption: "You need to google",
          link: "https://google.com",
        },
      ],
    };
  },
  provide(){
    return{
        resourses: this.storedResourses,
        addResourse: this.addResourse,
        deleteResourse: this.removeResourse
    }
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
    addResourse(title,desciption,url){
      const newResourse={
        id: new Date().toISOString(),
        title: title,
        desciption: desciption,
        link: url
      }
      this.storedResourses.unshift(newResourse);
      this.selectedTab='stored-resourses'
    },
    removeResourse(id){
      const resIndex = this.storedResourses.findIndex(resourse=>resourse.id===id);
      this.storedResourses.splice(resIndex,1);
    }
  },
};
</script>