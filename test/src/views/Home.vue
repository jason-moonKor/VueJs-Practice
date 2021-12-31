<template>
	<div>
		<h1>Welcome to my {{ title2 }}</h1>
		<input type="text" v-model="input1" />
		<button type="button" @click="getData">Get</button>
		<button type="button" @click="setData">Set</button>

		<select class="form-control" v-model="region" @change="changeRegion">
			<option :key="i" :value="d.v" v-for="(d, i) in options">{{ d.t }}</option>
		</select>

		<!--v-if , v-show 는 값이 true일때 보여짐-->
		<table class="table table-bordered" v-show="tableShow">
			<tr :key="i" v-for="(d, i) in options">
				<td>{{ d.v }}</td>
				<td>{{ d.t }}</td>
			</tr>
		</table>
	</div>
</template>
<script>
export default {
	data() {
		return {
			title: "JASON VUE JS TEST",
			title2: "INCHOEN",
			input1: "abccasdasdd",
			options: [
				{v: "S", t: "Seoul"},
				{v: "J", t: "Jeju"},
				{v: "B", t: "Busan"}
			],
			region: "S",
			tableShow: true
		};
	},
	watch: {
		//변수안에 값이 바뀔때마다 바로 캐치할수있는 기능 * 중요함
		input1() {
			if (this.input1 === "1234") {
				alert("빡큐");
			}
		}
	},
	methods: {
		getData() {
			alert(this.input1);
		},
		setData() {
			this.input1 = "12345";
		},
		changeRegion() {
			alert(this.region);
		}
	},
	beforeCreate() {
		console.log("beforeCreate");
	},
	created() {
		console.log("created");
	},
	beforeMount() {
		console.log("beforeMount");
	},
	mounted() {
		console.log("mounted");
	},
	beforeUpdate() {
		console.log("beforeUpdate");
	},
	updated() {
		console.log("updated");
	},
	beforeDestroy() {
		console.log("beforeDestroy");
	},
	destroyed() {
		console.log("destroyed");
	}
};
</script>
