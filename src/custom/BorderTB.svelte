<script>
    export let borderRadius;
</script>
<div>
    <label for="inputWidth">Border Radius</label>
    <input type="text" id="inputWidth" bind:value={borderRadius}/>
</div>


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
        width: 100%; /* Make the input field take the full width of the container */
        box-sizing: border-box; /* Include padding and border in the element's total width and height */
    }
</style>