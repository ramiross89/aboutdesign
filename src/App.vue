<template>
  <div id="app">
    <NavBar />
    <router-view/>
  </div>
</template>

<script>
// @ is an alias to /src
import NavBar from "@/components/navbar/NavBar.vue";

export default {
  name: "App",
  components: {
    NavBar
  }
};
</script>