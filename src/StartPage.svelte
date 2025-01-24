<script>
    import ColourWheel from './ColourWheel.svelte';
    import Shapes from './shapes.svelte';
    import ColourLetter from './ColourLetter.svelte';
    import Star from './Star.svelte';
    import Navbar from './Navbar.svelte';
    import WidthTb from './custom/WidthTB.svelte';
    import HeightTb from './custom/HeightTB.svelte';
    import BorderTb from './custom/BorderTB.svelte';
    import Create from './custom/Create.svelte';

    let savedColor = { r: 225, g: 225, b: 225, a: 1 };
    let customHeight = '100px';
    let customWidth = '100px';
    let customBorder = '100px';
    let shapes = [];

    function createShape() {
        shapes = [...shapes, { width: customWidth, height: customHeight, borderRadius: customBorder, savedColor }];
        
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
        <Shapes width={shape.width} height={shape.height} borderRadius={shape.borderRadius} savedColor={savedColor}/>
    {/each}
    
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
</style>