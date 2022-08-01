<script lang="ts">
	import { createEventDispatcher } from 'svelte';
	import Button from './Button.svelte';

	const dispatch = createEventDispatcher();
</script>

<div class="home">
	<div class="title">Theme Generator</div>
	<div class="subtitle">Generates themes for game jams, or any other competition</div>
	<Button text="Generate a theme" on:button_clicked={() => dispatch('generate_theme')} />
</div>

<style>
	.home {
		text-align: center;
	}

	.title {
		font-size: 4.8em;
		font-weight: 700;
	}

	.subtitle {
		font-size: 2em;
		font-weight: 500;
	}
</style>
