<script>
    import { Rive, Layout, Fit, Alignment } from "@rive-app/canvas";
    import { onMount } from "svelte";

    
    export let src;
    export let autoplay = true;
    export let stateMachine;
    export let cleanRive = false;

    let machine = "State Machine 1";  
    if (stateMachine) {
            machine = stateMachine;
        }
    onMount(() => {
        const riveCanvas = new Rive({
            src: src,
            // Or the path to a public Rive asset
            // src: '/public/example.riv',
            canvas: document.getElementById("riv"),
            autoplay: autoplay,
            stateMachines: machine,
            layout: new Layout({
                fit: Fit.Contain,
                alignment: Alignment.Center,
            }),
            onLoad: () => {riveCanvas.resizeDrawingSurfaceToCanvas()},
            shouldDisableRiveListeners: false,
        });
        if (cleanRive) {
            riveInstance.cleanup();
        }
    });
</script>

<canvas id="riv"></canvas>