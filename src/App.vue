<template>
 <div id="app">
  <Main />
  <sidebar />
 </div>
</template>

<script>
import Main from "./components/main/Main";
import Sidebar from "./components/sidebar/Sidebar.vue";

export default {
 components: {
  Sidebar,
  Main,
 },
};
</script>
