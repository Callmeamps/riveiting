<script>
    import RiveCanvas from "../RiveCanvas.svelte";
    export let offscreenRenderer = false;
</script>

<RiveCanvas 
    src="./simple-eye.riv"
    stateMachine="state_machine" 
    offscreenRenderer={offscreenRenderer} 
/>