<script>
 import RiveCanvas from "../RiveCanvas.svelte";
 export let offscreenRenderer = false;
</script>
<RiveCanvas src="./scenicButton.riv"    
    stateMachine="state_machine" 
    offscreenRenderer={offscreenRenderer} 
/>