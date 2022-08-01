<script lang="ts">
	import { onMount } from 'svelte';
	import { Confetti } from 'svelte-confetti';

	export let theme: string;

	const sleep = (ms = 2000) => new Promise((r) => setTimeout(r, ms));

	let confettisShowDelay: boolean = false;

	onMount(async () => {
		await sleep(1500);
		confettisShowDelay = true;
	});
</script>

<div class="theme_page">
	<!-- Top -->
	<div>
		<!-- Empty div -->
	</div>

	<!-- Center -->
	<div style="text-align: center;">
		<div class="label">And the theme is...</div>
		<div class="theme">
			{theme}
		</div>
	</div>

	<!-- Bottom -->
	<div class="confettis">
		{#if confettisShowDelay}
			<Confetti cone infinite x={[-1, 1]} y={[0.75, 1.5]} amount="200" size="12" />
		{/if}
	</div>
</div>

<style>
	.theme_page {
		height: 95%;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
	}

	.label {
		font-size: 1.8em;
		font-weight: 500;
		animation: label-animation 3s;
	}

	@keyframes label-animation {
		0%,
		50% {
			transition-timing-function: cubic-bezier(0.65, 0, 0.47, 0.99);
			font-size: 3.6em;
			font-weight: 700;
		}

		100% {
			transition-timing-function: cubic-bezier(0.65, 0, 0.47, 0.99);
			font-size: 1.8em;
			font-weight: 500;
		}
	}

	.theme {
		padding: 20px;
		font-size: 4.8em;
		font-weight: 700;
		animation: theme-animation 3s;
	}

	@keyframes theme-animation {
		0%,
		50% {
			transition-timing-function: cubic-bezier(0.65, 0, 0.47, 0.99);
			font-size: 0em;
			font-weight: 400;
		}

		100% {
			transition-timing-function: cubic-bezier(0.65, 0, 0.47, 0.99);
			font-size: 4.8em;
			font-weight: 700;
		}
	}
</style>
