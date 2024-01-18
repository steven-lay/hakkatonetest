<script>
	const shuffleArray = (array) => {
		for (let i = array.length - 1; i > 0; i--) {
			const j = Math.floor(Math.random() * (i + 1));
			[array[i], array[j]] = [array[j], array[i]];
		}
	};

	const pickRandomElement = () => {
		if (shuffledElements.length === 0) {
			shuffledElements = [...elements];
			shuffleArray(shuffledElements);
		}

		currentElement = shuffledElements.pop();

		remainingElements = shuffledElements.length;
	};

	const elements  = [
		"医", "妻", "车", "抽",
		"余", "词", "茶", "除",
		"意", "趣", "岔", "臭",
		"雨", "取", "扯", "暑",
		"一", "七", "杀", "出",
		"翼", "疾", "舌", "捽"
	]

	let shuffledElements = [];
  	let currentElement = "";
	  let remainingElements;

</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	{#if currentElement == ''}
		<p>Click below</p>
	{:else}
		<h1>{currentElement}</h1>
	{/if}
	<button on:click={pickRandomElement}>Click me</button>
	<button on:click={pickRandomElement}>Change array</button>
	<p>Remaining Elements: {remainingElements}</p>



</section>

<style>
	p {
		font-size: 2rem;
		text-align: center;
	}

	h1 {
		font-size: 15rem;
		text-align: center;
		margin-bottom: 1rem;
	}
</style>
