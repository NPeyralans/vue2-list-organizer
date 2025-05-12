<!-- App.vue -->
<template>
  <div id="app">
	  <Navbar />
	  <router-view :key="$route.fullPath"/>
	</div>
</template>

<script lang="ts">
import Vue from 'vue';
import Navbar from '@/components/Navbar.vue';

export default Vue.extend({
  name: 'App',
  components: {
	Navbar,
  },
  mounted(){
	console.log("The App.vue file has mounted.");
  }
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
