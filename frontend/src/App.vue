<template>
  <div id="app" class="d-flex flex-column">
    <Navigation />
    <div class="container">
      <router-view />
    </div>
    <Footer />
  </div>
</template>

<script>
import Navigation from "components/navigation";
import { REQUEST_TODOS } from "actions/user";
import Footer from "./components/footer/index.vue";

export default {
  components: {
    Footer,
    Navigation
  },
  name: "app",
  created: function() {
    if (this.$store.getters.isAuthenticated) {
      this.$store.dispatch(REQUEST_TODOS);
    }
  },
};
</script>

<style>
#app{
  min-height: 100vh;
}
body {
  margin: 0;
  font-family: "Roboto", sans-serif;
  color: #2e426b;
}
ul {
  margin: 0;
  padding: 0;
  list-style-type: none;
}
</style>

<style scoped>

</style>
