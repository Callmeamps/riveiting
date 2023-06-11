<script>
    import { Rive } from "@rive-app/canvas";
    import { onMount } from "svelte";
    import { AppBar } from "@skeletonlabs/skeleton";

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
        riveInstance.cleanup();
    });


</script>

<AppBar>
    <svelte:fragment slot="lead"><img src="./favicon.png" alt=""></svelte:fragment>
    <svelte:fragment slot="trail"><canvas id="riv" width="150" height="75">
        Subscribe
    </canvas></svelte:fragment>
</AppBar>