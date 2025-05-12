<!-- ListCard.vue -->
<template>
	<div class="list-card" :style="{ backgroundColor: bgColor }">
		<h3>{{ title }}</h3>

		<form @submit.prevent="addItem" class="item-form">
			<input 
				v-model="newItem"
				type="text"
				placeholder="Add item"
				class="item-input"
			/>
			<button type="submit" class="add-item-btn">+</button>
		</form>

		<ul class="item-list">
			<li v-for="(item, index) in items" :key="index">
				<label>
					<input type="checkbox" v-model="item.checked" />
					<space :class="{ checked: item.checked }">{{ item.text }}</space>
				</label>
			</li>
		</ul>
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
		return {
			newItem: '',
			items: []
		};
	},
	methods: {
		addItem() {
			if (this.newItem.trim() !== ''){
				this.items.push({
					text: this.newItem,
					checked: false
				});
				this.newItem = '';
			}
		}
	},
	mounted(){
		console.log("ListCard.vue has been mounted.");
	}
});
</script>

<style scoped>

.list-card {
	width: 100%;
	max-width: 500px;
	flex: 1 1 45%;
	padding: 15px;
	border-radius: 8px;
	box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
	box-sizing: border-box;
}

.list-card h3 {
	margin-bottom: 10px;
}

.item-form {
	display: flex;
	gap: 8px;
	margin-bottom: 10px;
}

.item-input {
	flex: 1;
	padding: 6px;
	font-size: 14px;
}

.add-item-btn {
	padding: 6px 12px;
	background-color: #2f855a;
	color: white;
	border: none;
	border-radius: 4px;
	cursor: pointer;
}

.item-list {
	list-style: none;
	padding: 0;
	margin: 0;
	text-align: left;
}

.item-list li {
	margin-bottom: 6px;
}

.checked {
	text-decoration: line-through;
	color: gray;
}
</style>
