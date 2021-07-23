<template>
	<div class="time">{{ time }}</div>
</template>

<script>
	export default {
		data() {
			return {
				time: null,
			};
		},
		methods: {
			getTime() {
				let hours, timeOfTheDay;
				let minutes = new Date(Date.now()).getMinutes();
				if (minutes < 9) minutes = '0'.concat(minutes);
				if (new Date(Date.now()).getHours() > 12) {
					hours = new Date(Date.now()).getHours() - 12;
					timeOfTheDay = 'pm';
				} else {
					hours = new Date(Date.now()).getHours();
					timeOfTheDay = `am`;
				}
				this.time = `${hours}:${minutes}${timeOfTheDay}`;
			},
		},
		mounted() {
			setInterval(this.getTime, 1000);
		},
	};
</script>

<style>
	.time {
		color: white;
		padding: 3px;
		/* margin-bottom: 1rem; */
		position: absolute;
		top: 5px;
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
</style>
