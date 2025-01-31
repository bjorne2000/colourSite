<script>
    export let shapes = [];

    let saveName = '';

    function saveToLocalStorage() {
        if (saveName.trim() === '') {
            alert('Please enter a name for your save.');
            return;
        }
        if (window.confirm(`Are you sure you want to save the shapes as "${saveName}"?`)) {
            
            localStorage.setItem(saveName, JSON.stringify(shapes));
            alert(`Shapes saved to local storage as "${saveName}"`);
            saveName = '';
        }
    }
</script>

<div>
    <label for="saveName">Save Name:</label>
    <input id="saveName" type="text" bind:value={saveName} placeholder="Enter save name" />
    <button on:click={saveToLocalStorage}>Save Shapes</button>
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

    input {
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