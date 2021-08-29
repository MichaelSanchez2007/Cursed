<script>
	import Quiz from '../components/Quiz.svelte';
</script>

<h1>How Smart Are You 😊</h1>
<h2>Quiz</h2>

<Quiz />

<style>
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@600&display=swap');
	@import url('https://fonts.googleapis.com/css2?family=IBM+Plex+Sans+KR:wght@300&family=Poppins:wght@600&display=swap');
    :global(h1) {
        text-align: center;
        font-family: 'Poppins',sans-serif;
        letter-spacing: 2px;
        filter: contrast(1.5);
    }
    :global(h2) {
        text-align: center;
        font-family: 'IBM Plex Sans KR', sans-serif;
        letter-spacing: 5px;
    }
</style>

