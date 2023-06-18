<script>
    import RiveCanvas from "$lib/RiveCanvas.svelte";
    import allTriggers from "$lib/RiveCanvas.svelte";

    export const morpherTriggers = allTriggers

</script>
<RiveCanvas 
    src="./icon-morph.riv" 
    canvas="icon-morph"
    stateMachine="state_machine" 
/>