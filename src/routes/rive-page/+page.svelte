<script>
    // import BrownBubble from "../../lib/canvases/BrownBubble.svelte";
	import IconMorph from "../../lib/canvases/IconMorph.svelte";
    import morpherTriggers from "../../lib/canvases/IconMorph.svelte";
    // import SceneToggle from "../../lib/canvases/SceneToggle.svelte";
</script>

<div class="flex card w-screen m-3 p-9 variant-ringed-primary h-full">
    <div class="-z-10 relative">
        <IconMorph />
    </div>
    <div >
        <button on:click={morpherTriggers[0].fire()} class="btn absolute z-10 variant-filled-primary">Big Button</button>
    </div>
</div>
