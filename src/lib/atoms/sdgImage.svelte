<script>
	export let data;

	// console.log(data);
</script>

<a href="https://sdgs.un.org/goals">
	<img class="susDevGoal" src={data.wish.image.image.url} alt="Sustainable development goals" />
</a>

<style>
	.susDevGoal {
		max-width: 50px;
		max-height: 50px;
		margin: 1em;
	}
	.susDevGoal:hover {
		animation-name: grow;
		animation-duration: 2s;
		animation-fill-mode: forwards; /* Stop the animation and keep the styles of the last keyframe when finished */
	}

	@keyframes grow {
		0% {
			transform: scale(1);
		}
		100% {
			transform: scale(2);
		}
	}
</style>
