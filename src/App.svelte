<script lang="ts">
	import Home from './lib/Home.svelte';

	function generateTheme() {
		console.log('generate theme');
	}
</script>

<div class="app">
	<Home on:generate_theme={generateTheme} />
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
