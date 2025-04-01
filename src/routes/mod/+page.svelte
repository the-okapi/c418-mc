<script>
	import '$lib/app.css';

	let mod = $state();
	let fabricApi = $state();
</script>

<a href="/c418-1.0.0.jar" hidden bind:this={mod}>Download JAR file</a>
<a href="/fabric-api-0.116.1+1.21.4.jar" hidden bind:this={fabricApi}>Download Fabric API</a>

<button onclick={() => mod.click()}>Download JAR File</button>

<button onclick={() => fabricApi.click()}>Download Fabric API</button>

<p>
	Mod is build for Minecraft Java 1.21.4 with Fabric Loader<br />
	It requires Fabric API
</p>

<h4>To Use</h4>
<ul>
	<li>Intall Fabric Loader for Minecraft 1.21.4</li>
	<li>Put both JAR file and Fabric api in minecraft mods folder</li>
</ul>

<style>
	:root {
		background-color: #e80200;
		color: white;
		font-family: 'Minecraft Seven';
		font-size: 1.25em;
	}
	button {
		background-color: white;
		color: black;
		font-family: 'Minecraft Seven';
		border: none;
		padding: 2vh 2vw;
		font-size: 1.25em;
		border-radius: 2vh;
		cursor: pointer;
	}
	button:hover {
		background-color: gainsboro;
	}
</style>
