<template>
	<h1>{{ title }}</h1>
	<Modal :modalContent="saleModal" />
	<br />
	<input type="text" ref="name" />
	<button @click="handleClick">click me</button>
</template>

<script>
import Modal from './components/Modal.vue';
export default {
	components: { Modal },
	name: 'App',
	data() {
		return {
			title: 'I am learning Vue3 Using CLI :)',
			saleModal: {
				header: 'Sing Up for the Giveaway!',
				text: 'Modal Content',
				theme: 'sale',
			},
		};
	},
	methods: {
		handleClick() {
			console.log(this.$refs.name);
			this.$refs.name.classList.add('active');
			this.$refs.name.focus();
		},
	},
};
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

h1 {
	border-bottom: 1px solid #ddd;
	display: inline-block;
	padding-bottom: 10px;
}
</style>
