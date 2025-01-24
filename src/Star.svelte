
<script>
        export let savedColor = 'red';
        export let size = '100px';
        export let padding = '10px';
        
        

        let currentColor = `rgba(${savedColor.r}, ${savedColor.g}, ${savedColor.b}, ${savedColor.a})`;

        function changeColor() {
        currentColor = `rgba(${savedColor.r}, ${savedColor.g}, ${savedColor.b}, ${savedColor.a})`;
    }
</script>

<div class="star-container"style="padding: {padding};" on:click={changeColor} on:keydown={(e) => e.key === 'Enter' && changeColor()} >
    <div class="star-border" style="width: calc({size} + 10px); height: calc({size} + 10px);" ></div>
    <div class="star" style="background-color: {currentColor}; width: {size}; height: {size}; "></div>
</div>

<style>
    .star-container {
        position: relative;
        display: inline-block;
        cursor: pointer; 
        outline: none; 
        
    }

    .star-container:focus {
        outline: none; 
    }

    .star, .star-border {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        clip-path: polygon(
            50% 0%,
            61% 35%,
            98% 35%,
            68% 57%,
            79% 91%,
            50% 70%,
            21% 91%,
            32% 57%,
            2% 35%,
            39% 35%
        );
    }

    .star-border {
        background-color: black; /* Border color */
    }
</style>