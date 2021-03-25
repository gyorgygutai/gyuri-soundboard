<script>
	import PlayButton from "./PlayButton.svelte";

	const sounds = [
		"./audio/igen.mp3",
		"./audio/hohoho.mp3",
		"./audio/ohoho.mp3",
		"./audio/coppki.mp3",
		"./audio/tevagyaz.mp3",
	];

	let isPlaying = false;
	let audioElement;

	const pickRandomSound = (currentSound) =>
		sounds.filter((sound) => sound !== currentSound)[
			Math.floor(Math.random() * sounds.length)
		];

	const queueNextSound = () => {
		audioElement = new Audio(pickRandomSound(audioElement?.src));
		audioElement.preload = true;
	};

	queueNextSound();

	const handleClick = () => {
		audioElement.pause();
		audioElement.play();

		audioElement.addEventListener("play", () => {
			isPlaying = true;
		});

		audioElement.addEventListener("playing", () => {
			isPlaying = true;
		});

		audioElement.addEventListener("ended", () => {
			isPlaying = false;
			queueNextSound();
		});
	};
</script>

<main class="container">
	<PlayButton disabled={isPlaying} on:click={handleClick} />
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
