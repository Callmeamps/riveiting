<script>
    import RiveCanvas from "../RiveCanvas.svelte";
    import trigger from "../RiveCanvas.svelte"
    
    export const bubbleTriggers = trigger;
    console.log(bubbleTriggers)
</script>

<RiveCanvas 
src="./brownbubble.riv"
canvas="bubble"
stateMachine="ActiveMachine" 
/>