<script>
    import RiveCanvas from "$lib/RiveCanvas.svelte";
    export let offscreenRenderer = false;
</script>
<RiveCanvas 
    src="./icon-morph.riv" 
    canvas="icon-morph"
    stateMachine="state_machine" 
    offscreenRenderer={offscreenRenderer} 
/>