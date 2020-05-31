<template>
  <div id="app">
    <NavBar />
      <transition
        name="fade"
        mode="out-in">
        <router-view/>
      </transition>
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