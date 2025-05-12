<!-- Navbar.vue -->
<template>
	<nav class="navbar">
	  <h1>List Organizer</h1>
	  <div class="links">
		<router-link to="/">Home</router-link>
		<router-link to="/about">About</router-link>
	  </div>
	</nav>
</template>

<script>
import Vue from 'vue';

export default Vue.extend({
	name: 'Navbar',
	props: {

	},
	data() {
		return {};
	},
	methods: {

	},
	mounted(){
		console.log("Navbar.vue has been mounted.");
	}
});
</script>

<style>
.navbar {
  background-color: #2f855a;
  padding: 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  color: white;
}

.navbar .links a {
  color: white;
  text-decoration: none;
  margin-left: 1rem;
}

.navbar .links a:hover {
  background-color: #276749;
  padding: 0.5rem;
  border-radius: 5px;
}
</style>

