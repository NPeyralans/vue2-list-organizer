<!-- Home.vue -->
<template>
	<div class="home-container">
		<AddList @list-added="addList" />
		<div class="list-container">
			<ListCard
					v-for="(list, index) in lists"
					:key="index"
					:title="list.title"
					:bg="list.bg"
			/>
		</div>
	</div>
</template>

<script>
import Vue from 'vue';
import AddList from '@/components/AddList.vue';
import ListCard from '@/components/ListCard.vue';

export default Vue.extend({
	name: 'Home',
	components: {
		AddList,
		ListCard,
	},
	props: {

	},
	data() {
		return {
			lists: []
		};
	},
	methods: {
		addList(newList) {
			this.lists.push(newList);
		}
	},
	mounted(){
		console.log("Home.vue has been mounted.");
	}
});
</script>

<style scoped>
.home-container {
	padding: 20px;
}

.list-container {
	display: flex;
	flex-wrap: wrap;
	gap: 20px;
}
</style>
