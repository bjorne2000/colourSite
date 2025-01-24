<script>
    export let width; 
    export let height;  
    export let borderRadius;
    export let createShape;

    import HeightTb from "./HeightTB.svelte";
    import WidthTb from "./WidthTB.svelte";
    import BorderTb from "./BorderTB.svelte";
</script>

<div class="create-container">
    <WidthTb bind:width={width} />
    <HeightTb bind:height={height} />
    <BorderTb bind:borderRadius={borderRadius} />
    <button on:click={() => createShape(width, height, borderRadius)}>Create</button>
</div>

<style>
    .create-container {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        padding: 10px;
        background-color: #f9f9f9; 
        border: 1px solid #ddd; 
        border-radius: 5px; 
    }

    button {
        margin-top: 10px;
    }
</style>