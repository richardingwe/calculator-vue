<template>
	<div class="buttons">
		<div class="row">
			<span @click="clearAll" class="extra_operator clearAll text-dark">
				AC
			</span>
			<span @click="clearOne" class="clear extra_operator text-dark">
				<svg
					aria-hidden="true"
					focusable="false"
					data-prefix="fas"
					data-icon="backspace"
					class="svg-inline--fa fa-backspace fa-w-20"
					role="img"
					xmlns="http://www.w3.org/2000/svg"
					viewBox="0 0 640 512"
				>
					<path
						fill="currentColor"
						d="M576 64H205.26A63.97 63.97 0 0 0 160 82.75L9.37 233.37c-12.5 12.5-12.5 32.76 0 45.25L160 429.25c12 12 28.28 18.75 45.25 18.75H576c35.35 0 64-28.65 64-64V128c0-35.35-28.65-64-64-64zm-84.69 254.06c6.25 6.25 6.25 16.38 0 22.63l-22.62 22.62c-6.25 6.25-16.38 6.25-22.63 0L384 301.25l-62.06 62.06c-6.25 6.25-16.38 6.25-22.63 0l-22.62-22.62c-6.25-6.25-6.25-16.38 0-22.63L338.75 256l-62.06-62.06c-6.25-6.25-6.25-16.38 0-22.63l22.62-22.62c6.25-6.25 16.38-6.25 22.63 0L384 210.75l62.06-62.06c6.25-6.25 16.38-6.25 22.63 0l22.62 22.62c6.25 6.25 6.25 16.38 0 22.63L429.25 256l62.06 62.06z"
					></path>
				</svg>
			</span>
			<span
				@click="handleButtonClick"
				class="button extra_operator text-dark"
				data="%"
			>
				%
			</span>
			<span
				@click="handleButtonClick"
				class="button operator text-light"
				data="/"
			>
				÷
			</span>
		</div>
		<div class="row">
			<span
				@click="handleButtonClick"
				class="button number text-light"
				data="7"
			>
				7
			</span>
			<span
				@click="handleButtonClick"
				class="button number text-light"
				data="8"
			>
				8
			</span>
			<span
				@click="handleButtonClick"
				class="button number text-light"
				data="9"
			>
				9
			</span>
			<span
				@click="handleButtonClick"
				class="button operator text-light"
				data="*"
			>
				×
			</span>
		</div>
		<div class="row">
			<span
				@click="handleButtonClick"
				class="button number text-light"
				data="4"
			>
				4
			</span>
			<span
				@click="handleButtonClick"
				class="button number text-light"
				data="5"
			>
				5
			</span>
			<span
				@click="handleButtonClick"
				class="button number text-light"
				data="6"
			>
				6
			</span>
			<span
				@click="handleButtonClick"
				class="button operator text-light"
				data="-"
			>
				-
			</span>
		</div>
		<div class="row">
			<span
				@click="handleButtonClick"
				class="button number text-light"
				data="1"
			>
				1
			</span>
			<span
				@click="handleButtonClick"
				class="button number text-light"
				data="2"
			>
				2
			</span>
			<span
				@click="handleButtonClick"
				class="button number text-light"
				data="3"
			>
				3
			</span>
			<span
				@click="handleButtonClick"
				class="button operator text-light"
				data="+"
			>
				+
			</span>
		</div>
		<div class="row">
			<span
				@click="handleButtonClick"
				class="button number text-light double"
				data="0"
			>
				0
			</span>
			<span
				@click="handleButtonClick"
				class="button number text-light"
				data="."
			>
				.
			</span>
			<span @click="handleSolve" class="operator solve text-light">
				=
			</span>
		</div>
	</div>
</template>

<script>
	export default {
		methods: {
			handleButtonClick(e) {
				this.$emit('getButtonValue', e.target.attributes[1].value);
			},
			handleSolve() {
				this.$emit('solve');
			},
			clearAll() {
				this.$emit('clearAll');
			},
			clearOne() {
				this.$emit('clearOne');
			},
		},
	};
</script>

<style>
	.buttons {
		height: 70%;
		/* background-color: darkslategrey; */
	}
	.fa-backspace {
		width: 32px;
	}
	.row {
		display: flex;
		justify-content: space-between;
		margin: 12px 0;
	}

	.row span.button,
	.clear,
	.clearAll,
	.solve,
	.plus_minus {
		width: 70px;
		height: 70px;
		border-radius: 50%;
		display: flex;
		place-content: center;
		place-items: center;
		font-size: 1.5rem;
		font-weight: bold;
		cursor: pointer;
	}
	.row span.button:hover,
	.clear:hover,
	.clearAll:hover,
	.solve:hover,
	.plus_minus:hover {
		filter: brightness(70%);
	}

	.extra_operator {
		background-color: #a6a6a6;
	}
	.operator {
		background-color: #f1a43c;
	}
	.number {
		background-color: #333333;
	}

	.text-dark {
		color: black;
	}

	.text-light {
		color: white;
	}

	.row span.double {
		width: 140px;
		border-radius: 60px;
		display: flex;
		justify-content: flex-start;
		padding-left: 1.6rem;
	}

	@media only screen and (max-width: 600px) {
		.calculator_body {
			width: 100%;
			height: 100vh;
			background-color: rgb(7, 5, 10);
			padding: 2.3rem 0.7rem;
		}
		.row span.double {
			width: 170px;
		}
	}
</style>
