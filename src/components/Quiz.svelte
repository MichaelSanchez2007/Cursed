<script>
	import Problem from './Problem.svelte';

	const problems = [
		{
			question: `What is the type for this variable:\n <pre><code class="language-javascript">"21"</code></pre>`,
			answers: ['number', 'string', 'function'],
			correctAnswer: 'string'
		},
		{
			question: `What is the type for this variable:\n <pre><code class="language-javascript">21</code></pre>`,
			answers: ['number', 'string', 'function'],
			correctAnswer: 'number'
		},
		{
			question: `What is the type for this variable:\n <pre><code class="language-javascript">const yeet = () => 21</code></pre>`,
			answers: ['number', 'string', 'function'],
			correctAnswer: 'function'
		}
	];

	let selected = [];
	let success = false;

	function submit() {
		problems.forEach((problem, i) => {
			const selectedAnswer = problem.answers[selected[i]];
			const correct = problem.correctAnswer === selectedAnswer;

			if (!correct) window.close();
			else success = true;
		});
	}
</script>

{#if success}
	<button on:click={() => window.location.reload()}>Restart</button>
	<img src="/Thumbs.jpg" alt="Thumbs up!" />
{:else}
	{#each problems as problem, i}
		<Problem {problem} bind:selected {i} />
	{/each}

	<button on:click={submit}>Submit</button>
{/if}

<style>
	img {
		width: 100vw;
		height: auto;
		filter: contrast(9999);
	}
	button {
		margin: auto;
		display: flex;
		color: lightblue;
		background: gray;
		filter: contrast(10);
		padding: 0.25rem 0.5rem;
	}
</style>
