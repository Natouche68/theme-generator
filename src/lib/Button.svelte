<script lang="ts">
	import { createEventDispatcher } from 'svelte';

	export let text: string;

	const dispatch = createEventDispatcher();
</script>

<button on:click={() => dispatch('button_clicked')}>
	{text}
</button>

<style>
	button {
		padding: 20px;
		margin: 30px;
		background: #0033ff;
		color: #fff;
		border-radius: 10px;
		border: none;
		font-size: 1.8em;
		font-family: 'Josefin Sans', 'Arial', sans-serif;
		transition: all 0.4s;
	}

	button:hover {
		background: #53ceff;
		color: #2c2c2c;
	}
</style>
