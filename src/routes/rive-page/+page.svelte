<script type="module">
    // import BrownBubble from "../../lib/canvases/BrownBubble.svelte";
	// import IconMorph from "../../lib/canvases/IconMorph.svelte";
    import RiveCanvas from "$lib/RiveCanvas.svelte";
    import trigger from "$lib/RiveCanvas.svelte";
    // import riveCanvas from "$lib/RiveCanvas.svelte";
    // import iconMorph from "../../lib/canvases/IconMorph.svelte";
    // import SceneToggle from "../../lib/canvases/SceneToggle.svelte";

    //const icon = riveCanvas;
    //const iconStateMachines = icon.stateMachineNames();
    //console.log(icon)
    //const iconTrigger = riveCanvas.stateMachineInputs("state_machine");
    //console.log(iconTrigger)
</script>

<div class="flex card w-screen m-3 p-9 variant-ringed-primary h-full">
    <div class="-z-10 relative">
        <RiveCanvas 
            src="./icon-morph.riv" 
            canvas="icon-morph"
            stateMachine="state_machine" 
        />
    </div>
    <div >
        <button on:click={trigger()} class="btn absolute z-10 variant-filled-primary">Big Button</button>
    </div>
</div>
