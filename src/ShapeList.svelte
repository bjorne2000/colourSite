<script>
    export let shapes = [];
    export let onSave = () => {};

    let selectedShapeIndex = null;
    let showEditArea = false;

    function editShape() {
        if (selectedShapeIndex !== null) {
            showEditArea = true;
        }
    }

    function closeEditArea() {
        showEditArea = false;
    }

    function saveShapes() {
        onSave(shapes);
        closeEditArea();
    }

    function deleteShape() {
        shapes = shapes.filter((_, index) => index !== selectedShapeIndex);
        selectedShapeIndex = null;
        onSave(shapes);
        closeEditArea();
    }

    function copyShape() {
        if (selectedShapeIndex !== null) {
            const shapeToCopy = shapes[selectedShapeIndex];
            shapes = [...shapes, { ...shapeToCopy }];
            onSave(shapes);
        }
    }
</script>

<div>
    <label for="shapelist">Shape list</label>
    <select id="shapelist" bind:value={selectedShapeIndex}>
        <option value={null} disabled selected>Select a shape</option>
        {#each shapes as shape, index}
            <option value={index}>Shape {index + 1}: {shape.width} x {shape.height}, Border: {shape.borderRadius}</option>
        {/each}
    </select>
    <button on:click={editShape}>Edit</button>
    <button on:click={copyShape}>Copy</button>
</div>

{#if showEditArea && selectedShapeIndex !== null}
    <div class="edit-area">
        <h3>Edit Shape {selectedShapeIndex + 1}</h3>
        <label for="width">Width:</label>
        <input id="width" type="text" bind:value={shapes[selectedShapeIndex].width} />
        
        <label for="height">Height:</label>
        <input id="height" type="text" bind:value={shapes[selectedShapeIndex].height} />
        
        <label for="borderRadius">Border Radius:</label>
        <input id="borderRadius" type="text" bind:value={shapes[selectedShapeIndex].borderRadius} />
        
        <label for="rotation">Rotation:</label>
        <input id="rotation" type="text" bind:value={shapes[selectedShapeIndex].rotation} />
        
        <button on:click={saveShapes}>Save</button>
        <button on:click={closeEditArea}>Close</button>
        <button on:click={deleteShape}>Delete</button>
    </div>
{/if}

<style>
    div {
        display: flex;
        flex-direction: column;
        margin: 10px;
        max-width: 300px; /* Set a maximum width for the container */
    }

    label {
        margin-bottom: 5px;
    }

    input {
        margin-bottom: 10px;
    }

    button {
        width: 70px;
    }

    .edit-area {
        margin-top: 20px;
        padding: 10px;
        border: 1px solid #ccc;
        background-color: #f9f9f9;
    }

    .edit-area h3 {
        margin-top: 0;
    }

    .edit-area label {
        display: block;
        margin-bottom: 5px;
    }
</style>