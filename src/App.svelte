<script lang="ts">
	import Home from './lib/Home.svelte';
	import ThemePage from './lib/ThemePage.svelte';
	import { themes } from './lib/themes';

	let currentAppState: AppState = 'home';
	let theme: string;

	function generateTheme() {
		theme = themes[Math.floor(Math.random() * themes.length)];
		currentAppState = 'show_theme';
	}
</script>

<div class="app">
	{#if currentAppState === 'home'}
		<Home on:generate_theme={generateTheme} />
	{:else if currentAppState === 'show_theme'}
		<ThemePage {theme} />
	{/if}
</div>

<style>
	.app {
		width: 100vw;
		height: 100vh;
		background: #00a2e7;
		color: #fff;
		font-family: 'Josefin Sans', 'Arial', sans-serif;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}
</style>
