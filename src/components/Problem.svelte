<script>
	export let selected = [];
	export let problem;
	export let i;

	let current = 1;

	$: selected[i] = current - 1;
</script>

<div class="problem">
	<h1>{@html problem.question}</h1>

	{#each problem.answers as answer, j}
		<label>
			<input type="radio" value={j + 1} bind:group={current} />
			{answer}
		</label>
	{/each}
</div>

<style>
	h1 {
		font-size: 0.9rem;
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.problem {
		display: flex;
		flex-direction: column;
		max-width: 600px;
		margin: 25px auto;
		border: 5px solid rgb(153, 196, 224);
		padding: 10px;
		text-align: center;
	}
	:global(pre),
	:global(code) {
		width: max-content;
		margin: auto;
		font-size: 14px;
	}
</style>
