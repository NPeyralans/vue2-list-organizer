<!-- AddList.vue -->
<template>
	<section class="form-section">
		<h2>Add a list</h2>
		<form @submit.prevent="submitForm">
			<div class="input-row">
			<input
					v-model="listName"
					type="text"
					placeholder="List name"
					class="input-field"
			/>
			<select v-model="listColor" class="input-field">
				<option disabled value="">Choose background color</option>
				<option value="red">Red</option>
				<option value="green">Green</option>
				<option value="Blue">Blue</option>
			</select>
			</div>
			<div class="button-wrapper">
				<button type="submit" class="add-button">Add List</button>
			</div>
		</form>
	</section>
</template>

<script>
import Vue from 'vue';

export default Vue.extend({
	name: 'AddList',
	props: {

	},
	data() {
		return {
			listName: '',
			listColor: ''
		};
	},
	methods: {
		submitForm(){
			if (this.listName && this.listColor){
				this.$emit('list-added', {
					title: this.listName,
					bg: this.listColor
				});
				this.listName = '';
				this.listColor = '';
			} else {
				alert('Please fill in both fields.');
			}
		}
	},
	mounted(){
		console.log("AddList has been mounted.");
	}
});
</script>

<style scoped>

form {
	display: flex;
	flex-direction: column;
	gap: 12px;
}

.form-section {
  background-color: #f0f0f0;
  padding: 20px;
  border-radius: 8px;
  margin-bottom: 30px;
}

.input-row {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.input-field {
  width: 100%;
  padding: 10px;
  font-size: 16px;
  box-sizing: border-box;
}

.button-wrapper {
  display: flex;
  justify-content: center; /* ✅ centers the button horizontally */
}

  @media (min-width: 600px) {
  .input-row {
    flex-direction: row;
  }

  .input-field {
    flex: 1;
    width: auto;
  }
}

.add-button {
  align-self: flex-start;
  padding: 10px 20px;
  background-color: #2f855a;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

.add-button:hover {
  background-color: #276749;
}

</style>
