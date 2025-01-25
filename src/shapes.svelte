<script>
    export let savedColor = { r: 255, g: 255, b: 255, a: 1 }; // Default color
    export let loadColor = { r: 100, g: 100, b: 100, a: 1};
    export let width; // Default width
    export let height;  // Default height
    export let borderRadius;
    export let rotation;
    export let topMargin;
    export let leftMargin;
    export let rightMargin;
    export let bottomMargin;


    export let left = '0px';
    export let top = '0px';
    
    let isDragging = false;
    let offsetX, offsetY; 
    let currentColor;
    $: currentColor = `rgba(${loadColor.r}, ${loadColor.g}, ${loadColor.b}, ${loadColor.a})`;

    function handleMouseDown(event) {
        isDragging = true;
        offsetX = event.clientX - parseInt(left);
        offsetY = event.clientY - parseInt(top);
        window.addEventListener('mousemove', handleMouseMove);
        window.addEventListener('mouseup', handleMouseUp);
    }

    function handleMouseMove(event) {
        if (isDragging) {
            left = `${event.clientX - offsetX}px`;
            top = `${event.clientY - offsetY}px`;
        }
    }
    function handleMouseUp() {
        isDragging = false;
        window.removeEventListener('mousemove', handleMouseMove);
        window.removeEventListener('mouseup', handleMouseUp);
    }
    

    function changeColor() {
        currentColor = `rgba(${savedColor.r}, ${savedColor.g}, ${savedColor.b}, ${savedColor.a})`; 
    }
</script>

<button
    class="rectangle"
    on:click={changeColor}
    on:keydown={(e) => e.key === 'Enter' && changeColor()}
    style="background-color: {currentColor}; width: {width}; height: {height};
     border-radius: {borderRadius}; rotate: {rotation}; margin-top: {topMargin}; 
     margin-left: {leftMargin}; margin-right: {rightMargin}; margin-bottom: {bottomMargin};
     position: absolute; left: {left}; top: {top};" 
    on:mousedown={handleMouseDown}>
    </button>

<style>
    .rectangle {
        
        border: 2px solid rgb(15, 15, 15);
        cursor: pointer; /* Change cursor to pointer to indicate it's clickable */
        outline: none; /* Remove the default focus outline */
        cursor: move;
        display: inline-block;
        
    }
    .rectangle:active {
        cursor: grabbing;
    }
    .rectangle:focus {
        outline: none; /* Ensure no outline when focused */
    }
</style>