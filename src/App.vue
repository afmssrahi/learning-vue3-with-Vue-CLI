<template>
	<h1>{{ title }}</h1>
	<p>Welcome...</p>
	<button @click="toggleModal">Open Modal</button>
	<div v-if="showModal">
		<Modal :theme="sale" @close="toggleModal">
			<h1>This Modal Header</h1>
			<p>Modal Content</p>
			<template v-slot:links>
				<a href="#">SingUp </a>
				<a href="#">More Info</a>
			</template>
		</Modal>
	</div>

	<br />
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
			theme: 'sale',
			showModal: false,
		};
	},
	methods: {
		handleClick() {
			console.log(this.$refs.name);
			this.$refs.name.classList.add('active');
			this.$refs.name.focus();
		},
		toggleModal() {
			this.showModal = !this.showModal;
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
