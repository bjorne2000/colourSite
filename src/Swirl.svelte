<script>

    import ColourWheel from './ColourWheel.svelte';
	import Shapes from './shapes.svelte';
    import ColourLetter from './ColourLetter.svelte';
    import Star from './Star.svelte';
    import WidthTb from './custom/WidthTB.svelte';
    import HeightTb from './custom/HeightTB.svelte';
    import BorderTb from './custom/BorderTB.svelte';
    import Create from './custom/Create.svelte';
	let savedColor = { r: 225, g: 225, b: 225, a: 1 };

    let customHeight = '100px';
    let customWidth = '100px';
    let customBorder = '100px';
    
    let circleWidth = '100px';
    let circleHeight = '100px';
    let mediumRectangleWidth = '100px';
    let mediumRectangleHeight = '50px';
</script>


<div class="left">
    <ColourWheel --picker-height="500px" --picker-width="50px" bind:savedColor={savedColor}/>		
    <Create bind:width={customWidth} bind:height={customHeight} bind:borderRadius={customBorder} />
</div>
<div class="content">
    <div>
        
        <div class="shapes-container">
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'500px'} topMargin={'80px'} rotation={'147deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'0px'} topMargin={'10px'} rotation={'169deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'5px'} topMargin={'10px'} rotation={'191deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'0px'} topMargin={'72px'} rotation={'207deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-30px'} topMargin={'183px'} rotation={'230deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-90px'} topMargin={'350px'} rotation={'253deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-155px'} topMargin={'535px'} rotation={'274deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-250px'} topMargin={'710px'} rotation={'310deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-350px'} topMargin={'800px'} rotation={'350deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-370px'} topMargin={'815px'} />
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-371px'} topMargin={'790px'} rotation={'17deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-350px'} topMargin={'696px'} rotation={'40deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-295px'} topMargin={'545px'} rotation={'67deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-190px'} topMargin={'360px'} rotation={'110deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-80px'} topMargin={'200px'} rotation={'134deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-15px'} topMargin={'100px'} rotation={'165deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'15px'} topMargin={'94px'} rotation={'190deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-9px'} topMargin={'175px'} rotation={'220deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-65px'} topMargin={'325px'} rotation={'245deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-120px'} topMargin={'510px'} rotation={'260deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-230px'} topMargin={'680px'} rotation={'315deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-347px'} topMargin={'760px'} rotation={'354deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-370px'} topMargin={'760px'} rotation={'7deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-360px'} topMargin={'690px'} rotation={'35deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-300px'} topMargin={'540px'} rotation={'70deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-180px'} topMargin={'350px'} rotation={'110deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-60px'} topMargin={'200px'} rotation={'150deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'1px'} topMargin={'165px'} rotation={'189deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-8px'} topMargin={'244px'} rotation={'220deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-80px'} topMargin={'400px'} rotation={'255deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-200px'} topMargin={'580px'} rotation={'300deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-325px'} topMargin={'690px'} rotation={'345deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-360px'} topMargin={'669px'} rotation={'30deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-300px'} topMargin={'530px'} rotation={'70deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-170px'} topMargin={'350px'} rotation={'120deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-35px'} topMargin={'245px'} rotation={'170deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-10px'} topMargin={'315px'} rotation={'230deg'}/>
            <Shapes {savedColor} width={'180px'} height={'35px'} leftMargin={'-130px'} topMargin={'490px'} rotation={'280deg'}/>
            <Shapes {savedColor} width={'135px'} height={'35px'} leftMargin={'-245px'} topMargin={'625px'} rotation={'330deg'}/>
            <Shapes {savedColor} width={'135px'} height={'35px'} leftMargin={'-270px'} topMargin={'625px'} rotation={'30deg'}/>
            <Shapes {savedColor} width={'135px'} height={'35px'} leftMargin={'-218px'} topMargin={'510px'} rotation={'80deg'}/>
            <Shapes {savedColor} width={'135px'} height={'35px'} leftMargin={'-110px'} topMargin={'370px'} rotation={'120deg'}/>
            <Shapes {savedColor} width={'170px'} height={'170px'} borderRadius={'1000px'} leftMargin={'-20px'} topMargin={'400px'}/>
        </div>

        <div>

        </div>   
        
    </div>
   
</div>


<style>

.left {
        position: absolute;
        top: 0;
        left: 0;
        display: flex;
        justify-content: center;
        align-items: flex-start;
        padding: 10px;
        margin-top: 60px; /* Adjust for navbar height */
    }

    .content {
        flex: 2;
        text-align: center;
        padding: 1em;
        max-width: 240px;
        margin: 0 auto;
        outline: none;
        margin-top: 60px; /* Adjust for navbar height */
    }
    .shapes-container {
        display: flex;
        
        align-items: flex-start;
       
    }

    @media (min-width: 640px) {
        .content {
            max-width: none;
        }
    }
</style>