<template>
	<div class="backdrop">
		<div class="modal" :class="{ sale: modalContent.theme === 'sale' }">
			<h1>{{ modalContent.header }}</h1>
			<p>{{ modalContent.text }}</p>
		</div>
	</div>
</template>

<script>
export default {
	name: 'Modal',
	props: ['modalContent'],
};
</script>

<style>
.modal {
	width: 400px;
	padding: 20px;
	margin: 100px auto;
	background: #fff;
	border-radius: 10px;
}

.backdrop {
	top: 0;
	position: fixed;
	background: rgba(0, 0, 0, 0.5);
	width: 100%;
	height: 100%;
}

h1 {
	color: #03cfb4;
	border: none;
	padding: 0;
}

.modal p {
	font-style: normal;
}

.modal.sale {
	background: crimson;
	color: #fff;
}

.modal.sale h1 {
	color: #fff;
}
</style>
