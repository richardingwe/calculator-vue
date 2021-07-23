<template>
	<div class="screen">
		<div class="digits">{{ digit }}</div>
	</div>
</template>

<script>
	export default {
		props: ['digit'],
		data() {
			return {
				// digit: 0,
			};
		},
	};
</script>

<style>
	.screen {
		/* background-color: darkred; */
		height: 30%;
		display: flex;
		justify-content: end;
		position: relative;

		border-radius: 4px;
		backdrop-filter: blur(5px);
		background: rgba(255, 255, 255, 0.1);
		animation: animate 10s linear infinite;
		box-shadow: 0 25px 45px rgba(0, 0, 0, 0.1);
		border: 1px solid rgba(255, 255, 255, 0.5);
		border-right: 1px solid rgba(255, 255, 255, 0.2);
		border-bottom: 1px solid rgba(255, 255, 255, 0.2);
		overflow-x: hidden;
	}

	.digits {
		font-size: 5rem;
		color: white;
		/* height: 90px; */
		position: absolute;
		bottom: 0.7rem;
		right: 1rem;
	}
</style>
