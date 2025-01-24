<script>
    import ColourWheel from './ColourWheel.svelte';
    import Shapes from './shapes.svelte';
    import Navbar from './Navbar.svelte';
    import Create from './custom/Create.svelte';
    import ShapeList from './ShapeList.svelte';

    let savedColor = { r: 225, g: 225, b: 225, a: 1 };
    let customHeight = '100px';
    let customWidth = '100px';
    let customBorder = '100px';
    let customRotate = '0deg';
    let shapes = [];

    function createShape() {
        shapes = [...shapes, { width: customWidth, height: customHeight, borderRadius: customBorder, rotation: customRotate, savedColor }];
    }

    function updateShapes(updatedShapes) {
        shapes = updatedShapes;
    }

</script>
<div class="container">
    <Navbar />
<div class="left">
    <ColourWheel --picker-height="500px" --picker-width="50px" bind:savedColor={savedColor}/>	
    <Create bind:width={customWidth} bind:height={customHeight} bind:borderRadius={customBorder} {createShape} />	
</div>
<div class="content">
    {#each shapes as shape}
    <Shapes width={shape.width} height={shape.height} borderRadius={shape.borderRadius} rotation={shape.rotation} savedColor={savedColor}/>
    {/each}
</div>
<div class="right">
    <ShapeList {shapes} onSave={updateShapes}/>
</div>
</div>

<style>
        .container {
        display: flex;
        flex-direction: row;
        margin-top: 60px; 
    }
    .left {
        display: flex;
        flex-direction: row;
        align-items: flex-start;
        width: 450px; 
        padding: 10px;
        background-color: #f0f0f0;
    }

    .content {
        flex: 1;
        margin-left: 500px; 
        padding: 20px;
        background-color: #fff; 
        margin-top: 60px;
        position: relative;
    }
    .right {
        position: absolute;
        top: 0;
        right: 0;
        padding: 10px;
        margin-top: 60px;
        background-color: #f0f0f0;
    }
</style>