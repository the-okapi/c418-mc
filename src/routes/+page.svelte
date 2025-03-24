<script lang="ts">
	import '$lib/app.css';

	import data from '$lib/data.json';

	import c418key from '$lib/images/c418_key.png';
	import c418bookshelf from '$lib/images/c418_bookshelf.png';

	let currentScroll = $state('title');

	let currentNum = $state(0);

	const back = '<';
	const next = '>';

	const content: any = data;

	function setScroll(scroll: string) {
		currentNum = 0;
		currentScroll = scroll;
	}
</script>

<nav>
	<h1>C418</h1>
	<div style="display: flex">
		<img src={c418key} alt="a key" class="smallImg" />
		<div class="fit">
			{#if currentScroll === 'title'}
				<button class="active button">Title Scroll</button>
			{:else}
				<button class="notActive button" onclick={() => setScroll('title')}>Title Scroll</button>
			{/if}
			{#if currentScroll === 'about'}
				<button class="active button">About Scroll</button>
			{:else}
				<button class="notActive button" onclick={() => setScroll('about')}>About Scroll</button>
			{/if}
			{#if currentScroll === 'music'}
				<button class="active button">Music Scroll</button>
			{:else}
				<button class="notActive button" onclick={() => setScroll('music')}>Music Scroll</button>
			{/if}
			{#if currentScroll === 'opinion'}
				<button class="active button">Opinion Scroll</button>
			{:else}
				<button class="notActive button" onclick={() => setScroll('opinion')}>Opinion Scroll</button
				>
			{/if}
		</div>
		<img src={c418bookshelf} alt="a bookshelf" class="smallImg" />
	</div>
</nav>

<main>
	<img src={`/images/${currentScroll}_scroll.png`} alt="the current scroll" class="currentScroll" />
	<div class="grid3">
		{#if currentNum !== 0}
			<button class="movementButton" onclick={() => currentNum--}>{back}</button>
		{:else}
			<div></div>
		{/if}
		<p class="mainText">{@html content[currentScroll].parts[currentNum]}</p>
		{#if currentNum + 1 < content[currentScroll].num}
			<button class="movementButton" onclick={() => currentNum++}>{next}</button>
		{:else}
			<div></div>
		{/if}
	</div>
</main>

<style>
	:global(body) {
		margin: 0;
		background-color: #e80200;
	}
	.grid3 {
		display: grid;
		grid-template-columns: 1fr 3fr 1fr;
		text-align: center;
	}
	h1 {
		font-family: 'Minecraft Ten';
		font-size: 5em;
		color: white;
		margin: 0;
		vertical-align: middle;
	}
	.fit {
		display: grid;
		grid-template-columns: 1fr 1fr 1fr 1fr;
	}
	.mainText {
		font-family: 'minecraft Seven';
		color: white;
		font-size: 2em;
		vertical-align: middle;
		text-align: center;
		margin: auto;
	}
	main {
		background-color: #027bff;
		height: calc(94vh - 5em);
		display: flex;
		text-align: center;
	}
	.currentScroll {
		image-rendering: pixelated;
		height: calc(93vh - 5em);
	}
	nav {
		background-color: #e80200;
		padding: 3vh;
		display: grid;
		grid-template-columns: 1fr 3fr;
	}
	.smallImg {
		image-rendering: pixelated;
		height: 5em;
	}
	.active {
		background-color: #027bff;
	}
	.notActive {
		background-color: #e80200;
		cursor: pointer;
	}
	.notActive:hover {
		background-color: #cc0300;
		cursor: pointer;
	}
	.button {
		color: white;
		border-radius: 2vh;
		padding: 2vh 2vw;
		font-size: 1.22em;
		font-family: 'Minecraft Seven';
		margin: auto 1vw;
		border: none;
	}
	.movementButton {
		color: white;
		border-radius: 2vh;
		padding: 2vh 2vw;
		font-size: 1.22em;
		font-family: 'Minecraft Seven';
		margin: auto;
		width: fit-content;
		border: none;
		background-color: #e80200;
		cursor: pointer;
	}
</style>
