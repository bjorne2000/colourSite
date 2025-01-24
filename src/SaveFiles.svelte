<script>
    import { onMount } from 'svelte';
    export let onLoad = () => {};

    let savedFiles = [];
    let selectedFile = '';

    onMount(() => {
        // Load saved files from local storage
        savedFiles = Object.keys(localStorage);
    });

    function loadFromLocalStorage() {
        if (selectedFile.trim() === '') {
            alert('Please select a file to load.');
            return;
        }
        const shapes = JSON.parse(localStorage.getItem(selectedFile));
        onLoad(shapes);
    }
</script>

<div>
    <label for="savedFiles">Saved Files:</label>
    <select id="savedFiles" bind:value={selectedFile}>
        <option value="" disabled selected>Select a file</option>
        {#each savedFiles as file}
            <option value={file}>{file}</option>
        {/each}
    </select>
    <button on:click={loadFromLocalStorage}>Load Shapes</button>
</div>

<style>
    div {
        display: flex;
        flex-direction: column;
        margin: 10px;
    }

    label {
        margin-bottom: 5px;
    }

    select {
        margin-bottom: 10px;
        padding: 5px;
        border: 1px solid #ccc;
        border-radius: 5px;
    }

    button {
        width: 100px;
        padding: 10px;
        background-color: #4CAF50;
        color: white;
        border: none;
        border-radius: 5px;
        cursor: pointer;
    }

    button:hover {
        background-color: #45a049;
    }
</style>