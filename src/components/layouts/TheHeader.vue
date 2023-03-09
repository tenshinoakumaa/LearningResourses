<template>
  <header>
    <h1>
      {{ title }}
    </h1>
  </header>
</template>


<script>
export default {
  props: ["title"],
};
</script>

<style scoped>
header {
  border-radius: 50px;
  margin: 0 auto;
  width: 90%;
  height: 5rem;
  background-color: #3a0061;
  display: flex;
  justify-content: center;
  align-items: center;
}

header h1 {
  color: rgb(255, 255, 255);
  margin: 0;
}
</style>