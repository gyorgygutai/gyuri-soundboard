<script>
	import PlayButton from "./PlayButton.svelte";

	const handleClick = () => {
		console.log("TODO");
	};
</script>

<main class="container">
	<PlayButton on:click={handleClick} />
</main>

<style>
	:global(*, *::after, *::before) {
		box-sizing: inherit;
	}

	:global(html) {
		font-size: 62.5%;
	}

	:global(body) {
		margin: 0;
		font-size: 2rem;
		box-sizing: border-box;
		color: rgba(0, 0, 0, 0.9);
		background-color: #fff;
		font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
			Helvetica, Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji",
			"Segoe UI Symbol";
	}

	@media (prefers-color-scheme: dark) {
		:global(body) {
			color: rgba(255, 255, 255, 0.9);
			background-color: rgba(0, 0, 0, 0.9);
		}
	}

	.container {
		height: 90vh;
		display: flex;
		align-items: center;
		justify-content: center;
	}
</style>
