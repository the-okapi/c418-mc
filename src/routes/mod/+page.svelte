<script>
    import '$lib/app.css';

    let a = $state();
</script>

<a href="/c418-1.0.0.jar" hidden bind:this={a}>Download JAR file</a>

<button onclick={() => a.click()}>Download JAR File</button>

<style>
    :root {
        background-color: #e80200;
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