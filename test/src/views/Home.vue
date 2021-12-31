<template>
	<div>
		<h1>Welcome to my {{ title2 }}</h1>
		<input type="text" v-model="input1" />
		<button type="button" @click="getData">Get</button>
	</div>
</template>
<script>
export default {
	data() {
		return {
			title: "JASON VUE JS TEST",
			title2: "INCHOEN",
			input1: "abccasdasdd"
		};
	},
	methods: {
		getData() {
			alert(this.input1);
		}
	}
};
</script>
