<script>
	import ColorPicker, {ChromeVariant} from 'svelte-awesome-color-picker';
  let hex = "#b29023"

let rgb = {
  "r": 178,
  "g": 144,
  "b": 35,
  "a": 1
}

let hsv = {
  "h": 46,
  "s": 80.5,
  "v": 69.6875,
  "a": 1
}

let color = "// instance of Colord"
export let savedColor = { r: 255, g: 255, b: 255, a: 1 };

function saveColor(){
  savedColor = { ...rgb, a: rgb.a };
  console.log(savedColor)
}

</script>

<div class="color-picker-container">
  <ColorPicker
      bind:hex
      bind:rgb
      bind:hsv
      bind:color
      position="responsive"
      components={ChromeVariant}
      sliderDirection="horizontal"
      isDialog={false}
  />
  <button on:click={saveColor}>Save Color</button>
</div>

<style>
  .color-picker-container {
      display: flex;
      flex-direction: column;
      align-items: center;
  }

  button {
      margin-top: 0.1em;
      border-radius: 10px;
      height: 50px;
      width: 100px;
      background-color: rgb(148, 191, 199);
  }
</style>

