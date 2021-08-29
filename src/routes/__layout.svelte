<script>
	import { browser } from '$app/env';
	import { onMount } from 'svelte';
	import Prism from 'prismjs';

	onMount(() => {
		if (browser)
			setTimeout(() => {
				Prism.highlightAll();
			});
	});
</script>

<slot />
