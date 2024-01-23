<script>
	import SdgImage from '../atoms/sdgImage.svelte';
	export let data;
	// console.log(data.wish.image.url);
</script>

<section class="container-susDevGoal">
	<img
		class="susDevGoal"
		src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/50/Sustainable_Development_Goal_01NoPoverty.svg/599px-Sustainable_Development_Goal_01NoPoverty.svg.png"
		alt="sustainable development goal 1"
	/>
	<SdgImage {data} />
</section>

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
	.container-susDevGoal {
		display: flex;
		flex-direction: row;
		margin-left: 2em;
	}
</style>
