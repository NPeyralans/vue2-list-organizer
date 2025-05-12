<!-- ListCard.vue -->
<template>
	<div class="list-card" :style="{ backgroundColor: bgColor }">
		<h3>{{ title }}</h3>
		<p>This is your list</p>
	</div>
</template>

<script>
import Vue from 'vue';

export default Vue.extend({
	name: 'ListCard',
	props: {
		title: String,
		bg: String
	},
	computed: {
		bgColor(){
			const map = {
				red: '#fdd',
				green: '#dfd',
				blue: '#ddf'
			};
			return map[this.bg] || '#eee';
		}
	},
	data() {
		return {};
	},
	methods: {

	},
	mounted(){
		console.log("ListCard.vue has been mounted.");
	}
});
</script>

<style scoped>
.list-card {
	padding: 15px;
	border-radius: 8px;
	width: 200px;
	box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

.list-card h3 {
	margin-bottom: 10px;
}
</style>
