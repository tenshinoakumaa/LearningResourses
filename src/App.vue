<template>
  <ul>
    <the-header title="Remember me"></the-header>
    <the-resourses></the-resourses>
  </ul>
</template>


<script>
import TheHeader from './components/layouts/TheHeader.vue'
import TheResourses from './components/learning-resourses/TheResourses.vue';


export default {
  components: {
    TheResourses,
    TheHeader
  },

};
</script>

<style>
body{
  background-color: rgb(255, 255, 255)
}
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap");

* {
  box-sizing: border-box;
}

html {
  font-family: "Roboto", sans-serif;
}

body {
  margin: 0;
}
ul{
  padding: 0 0 ;
}
</style>