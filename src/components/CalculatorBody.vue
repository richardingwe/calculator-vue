<template>
	<div class="calculator_body">
		<Time />
		<Screen :digit="digit" />
		<Buttons
			@getButtonValue="getButtonValue"
			@solve="solve"
			@clearAll="clearAll"
		/>
	</div>
</template>

<script>
	import Time from './Time.vue';
	import Screen from './Screen.vue';
	import Buttons from './Buttons.vue';

	export default {
		components: { Time, Screen, Buttons },
		data() {
			return {
				question: 0,
				digit: 0,
			};
		},
		methods: {
			getButtonValue(value) {
				// console.log(value);
				this.digit += value;
				if (this.digit[0] == '0') this.digit = this.digit.slice(1);
				this.question += value;
				if (this.question[0] == '0') this.question = this.question.slice(1);
			},
			solve() {
				this.digit = eval(this.question);
			},
			clearAll() {
				this.question = 0;
				this.digit = 0;
			},
		},
	};
</script>

<style>
	.calculator_body {
		width: 330px;
		height: 650px;
		background-color: rgb(7, 5, 10);
		padding: 2.3rem 0.7rem;
		position: relative;
	}
</style>
