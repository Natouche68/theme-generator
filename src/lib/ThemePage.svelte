<script lang="ts">
	export let theme: string;
</script>

<div class="theme_page">
	<div class="label">And the theme is...</div>
	<div class="theme">
		{theme}
	</div>
</div>

<style>
	.theme_page {
		text-align: center;
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
