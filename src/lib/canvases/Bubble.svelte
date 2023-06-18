<script>
    import RiveCanvas from "../RiveCanvas.svelte";
    export let offscreenRenderer = false;
</script>

<RiveCanvas 
src="./brownbubble.riv"
canvas="bubble"
stateMachine="state_machine" 
offscreenRenderer={offscreenRenderer} 
/>