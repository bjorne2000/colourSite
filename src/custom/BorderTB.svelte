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
        max-width: 300px; 
    }

    label {
        margin-bottom: 5px;
    }

    input {
        
        margin-bottom: 10px;
        width: 100%; 
        box-sizing: border-box; 
    }
</style>