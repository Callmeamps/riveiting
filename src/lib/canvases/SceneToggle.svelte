<script>
    import { Rive, Layout, Fit, Alignment } from "@rive-app/canvas";
    import { onMount } from "svelte";
    import { AppBar } from "@skeletonlabs/skeleton";

    
    export let cleanRive = false;

    onMount(() => {    
        const r = new Rive({
            src: "./scenicButton.riv",
            // Or the path to a public Rive asset
            // src: '/public/example.riv',
            canvas: document.getElementById("riv"),
            autoplay: true,
            stateMachines: "State Machine 1",
            onLoad: () => {
            r.resizeDrawingSurfaceToCanvas();
            },
            shouldDisableRiveListeners: false,
        });
        if (cleanRive) {
            riveInstance.cleanup();
        }
    });


</script>
<div class="w-screen flex rounded-md border-warning-100 border-t-0 justify-center">
    <canvas id="riv" width="150" height="75">
</div>