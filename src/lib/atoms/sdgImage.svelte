<script>
	export let data;

	// console.log(data);
</script>

<img class="susDevGoal" src={data.wish.image.image.url} alt="Sustainable development goals" />

<style>
	.susDevGoal {
		max-width: 50px;
		max-height: 50px;
		margin: 1em;
	}
</style>
