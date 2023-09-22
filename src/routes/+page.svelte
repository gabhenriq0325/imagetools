<script>
	import { onMount } from 'svelte';
	import static_image from './favicon.png?blur=1';

	let dynamic_image;
	let name = 'favicon';

	onMount(async () => {
		dynamic_image = (await import(`./${name}.png?blur=1`)).default;
	});
</script>

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>

<p>static import</p>
<img src={static_image} alt="Svelte logo" />

<p>dynamic import</p>
<img src={dynamic_image} alt="Svelte logo" />
