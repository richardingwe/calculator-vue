<template>
	<div class="container">
		<CalculatorBody />
	</div>
</template>

<script>
	import CalculatorBody from './components/CalculatorBody.vue';

	export default {
		name: 'App',
		components: { CalculatorBody },
	};
</script>

<style>
	* {
		margin: 0;
		padding: 0;
		box-sizing: border-box;
		font-family: montserrat;
	}

	.container {
		background-color: aliceblue;
		min-height: 100vh;
		display: flex;
		place-items: center;
		place-content: center;
	}
</style>
