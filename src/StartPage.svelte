<script>
    import SaveList from './SaveList.svelte';
    import SaveFiles from './SaveFiles.svelte';
    import ShapeList from './ShapeList.svelte';
    import Create from './custom/Create.svelte';
    import ColourWheel from './ColourWheel.svelte';
    import Shapes from './shapes.svelte';
    import Navbar from './Navbar.svelte';

    let savedColor = { r: 255, g: 255, b: 255, a: 1};
    let loadColor = { r: 100, g: 100, b: 100, a: 1};
    let customHeight = '100px';
    let customWidth = '300px';
    let customBorder = '10px';
    let customRotate = '0deg';
    let savingList = [];
    let combinedShapes = [];
    export let shapes = [];
    let loadShapes = [];
    console.log("loggar");

    function createShape() {
        const newShape = {
            width: customWidth,
            height: customHeight,
            borderRadius: customBorder,
            rotation: customRotate,
            loadTop: '0px',
            loadLeft: '0px',
            savedColor: { ...savedColor },
            loadColor: { ...loadColor }
        };
        shapes = [...shapes, newShape];
    }

    function updateShapes(updatedShapes) {
        shapes = updatedShapes;
    }

    function handleColorChange(event, index) {
        const colorString = event.detail.color;
        const colorMatch = colorString.match(/rgba?\((\d+), (\d+), (\d+)(?:, (\d+(\.\d+)?))?\)/);
        if (colorMatch) {
            const [_, r, g, b, a] = colorMatch;
            const colorObject = { r: parseInt(r), g: parseInt(g), b: parseInt(b), a: a ? parseFloat(a) : 1 };
            combinedShapes[index].savedColor = colorObject;
            combinedShapes[index].loadColor = colorObject;
            combinedShapes = [...combinedShapes];
        }
    }

    function handlePositionChange(event, index) {
        combinedShapes[index].loadTop = event.detail.top;
        combinedShapes[index].loadLeft = event.detail.left;
        combinedShapes = [...combinedShapes];
    }

    function loadShapesFromFile(loadedShapes) {
        console.log("funkar");

        loadShapes = loadedShapes.map(shape => ({
            ...shape,
            loadColor: shape.loadColor,
            loadTop: shape.loadTop,
            loadLeft: shape.loadLeft
        }));
        
        
    }


    $: combinedShapes = [...shapes, ...loadShapes];
</script>

<div class="container">
    <Navbar />
    <div class="left">
        
            <ColourWheel --picker-height="500px" --picker-width="50px" bind:savedColor={savedColor}/>    
        
        <Create bind:width={customWidth} bind:height={customHeight} bind:borderRadius={customBorder} bind:rotation={customRotate} bind:savedColor={savedColor} {createShape} />  
    </div>
    <div class="content"> 
     
        {#each combinedShapes as shape, index}
            <Shapes 
                width={shape.width} 
                height={shape.height} 
                borderRadius={shape.borderRadius} 
                rotation={shape.rotation} 
                savedColor={savedColor} 
                loadColor={shape.loadColor}
                loadTop={shape.loadTop}
                loadLeft={shape.loadLeft}
                on:colorChange={(event) => handleColorChange(event, index)}
                on:positionChange={(event) => handlePositionChange(event, index)}
            />
            
        {/each}


    </div>
    <div class="right">
        
        <ShapeList bind:shapes={combinedShapes} onSave={updateShapes}/>
        <SaveList bind:shapes={combinedShapes} />
        <SaveFiles onLoad={loadShapesFromFile} />
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
        background-color: #f0f0f0;
        padding-top: 60px;
    }
</style>