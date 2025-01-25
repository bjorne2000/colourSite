<script>
    export let width;
</script>
<div>
    <label for="inputWidth">width</label>
    <input type="text" id="inputWidth" bind:value={width} width="300px"/>
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