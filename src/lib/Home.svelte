<script lang="ts">
	import { createEventDispatcher } from 'svelte';
	import Button from './Button.svelte';

	const dispatch = createEventDispatcher();
	const sleep = (ms = 2000) => new Promise((r) => setTimeout(r, ms));

	let homeCss: string = 'home';

	async function buttonClicked() {
		homeCss = 'home not_visible';
		await sleep(1000);
		dispatch('generate_theme');
	}
</script>

<div class={homeCss}>
	<div class="title">Theme Generator</div>
	<div class="subtitle">Generates themes for game jams, or any other competition</div>
	<Button text="Generate a theme" on:button_clicked={buttonClicked} />
</div>

<style>
	.home {
		text-align: center;
		transition: all 1s;
	}

	.title {
		font-size: 4.8em;
		font-weight: 700;
	}

	.subtitle {
		font-size: 2em;
		font-weight: 500;
	}

	.not_visible {
		opacity: 0;
	}
</style>
