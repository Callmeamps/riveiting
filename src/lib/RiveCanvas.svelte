<script>
    import { Rive, Layout, Fit, Alignment } from "@rive-app/canvas";
    import { beforeUpdate, onMount } from "svelte";

    export let src;
    export let canvas;
    export let stateMachine = "State Machine 1";
    export let autoplay = true;
    export let cleanRive = false;
    export let offscreenRenderer = false;
    export let defaultLayout = new Layout({
                fit: Fit.Contain,
                alignment: Alignment.Center,
            });
    export let riveCanvas;
    export let allTriggers;
    export let trigger;

    if (!canvas) {
        canvas = "canvas";
    };

    beforeUpdate(() => {
        if (riveCanvas) {
            riveCanvas.cleanup();
        }
    })

    onMount(() => {
        riveCanvas = new Rive({
            src: src,
            // Or the path to a public Rive asset
            // src: '/public/example.riv',
            canvas: document.getElementById(canvas),
            autoplay: autoplay,
            stateMachines: stateMachine,
            layout: defaultLayout,
            shouldDisableRiveListeners: false,
            useOffscreenRenderer: offscreenRenderer,
            onLoad: () => {
                riveCanvas.resizeDrawingSurfaceToCanvas();
                 // Get the inputs via the name of the state machine
                 allTriggers = riveCanvas.stateMachineInputs(stateMachine);
                // Find the input you want to set a value for, or trigger
                trigger = allTriggers.find("StateMachineInput2").fire();

            },    
        });

        if (cleanRive) {
            riveCanvas.cleanup();
        }
    });
</script>

<canvas id={canvas}></canvas>
