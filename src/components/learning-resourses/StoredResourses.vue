<template>
  <ul>
    <learning-resourse
      v-for="resourse in resourses"
      :key="resourse.id"
      :id="resourse.id"
      :title="resourse.title"
      :description="resourse.desciption"
      :link="resourse.link"
    ></learning-resourse>
  </ul>
</template>


<script>
import LearningResourse from "./LearningResourse.vue";

export default {
  inject: ["resourses"],
  components: {
    LearningResourse,
  },
};
</script>

<style scoped>

ul {
  list-style: none;
  margin: 0;
  padding: 0;
  margin: auto;
  max-width: 40rem;
}
</style>