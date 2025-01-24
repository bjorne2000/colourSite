<!-- <script>
    export let width; 
    export let height;  
    export let borderRadius;

    import HeightTb from "./HeightTB.svelte";
    import WidthTb from "./WidthTB.svelte";
    import BorderTb from "./BorderTB.svelte";
    import Shapes from "../shapes.svelte";
    let savedColor = { r: 225, g: 225, b: 225, a: 1 };
    let shapes = [];

    function createShape() {
        shapes = [...shapes, {width, height, borderRadius}];
        console.log('Shape created', { width, height, borderRadius });
    }
    
</script>
<div class="create-container">
    <WidthTb bind:width={width} />
    <HeightTb bind:height={height} />
    <BorderTb bind:borderRadius={borderRadius} />
    <button on:click={createShape}>Create</button>

    {#each shapes as shape}
        <Shapes width={shape.width} height={shape.height} borderRadius={shape.borderRadius} />
    {/each}
</div>
<style>
    .create-container {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        padding: 10px;
        background-color: #f9f9f9; /* Optional: Add background color */
        border: 1px solid #ddd; /* Optional: Add border */
        border-radius: 5px; /* Optional: Add border radius */
    }

    button {
        margin-top: 10px;
    }
</style> -->


<!-- filepath: /home/bjorn/programmering/colour_site/src/custom/Create.svelte -->
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