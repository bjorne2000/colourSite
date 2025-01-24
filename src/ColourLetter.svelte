<script>
        export let savedColor = 'red';
        export let letter;
        

        let currentColor = `rgba(${savedColor.r}, ${savedColor.g}, ${savedColor.b}, ${savedColor.a})`;

        function changeColor() {
        currentColor = `rgba(${savedColor.r}, ${savedColor.g}, ${savedColor.b}, ${savedColor.a})`;
        console.log('Rectangle clicked, color changed to:', currentColor);

    }
</script>

<div class="letter-container" on:click={changeColor} on:keydown={(e) => e.key === 'Enter' && changeColor()}>
    <span class="letter" style="color: {currentColor};">{letter}</span>
</div>

<style>


    .letter-container {
        display: inline-block;
        padding: 10px;
        
        cursor: pointer;
        outline: none;
    }

    .letter-container:focus {
        outline: none;
    }

    .letter {
        display: inline-block;
        font-size: 7em; /* Make the letter big */
        font-weight: bold; /* Make the letter bold */
        padding: 0; /* Add some padding */

        background-clip: text;
        -webkit-background-clip: text;
        -webkit-text-stroke: 2px black;    
    }
</style>