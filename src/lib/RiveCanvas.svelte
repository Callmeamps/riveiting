<script>
    import { Rive, Layout, Fit, Alignment } from "@rive-app/canvas";
    import { onMount } from "svelte";

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
    let inputs;

    if (!canvas) {
        canvas = "canvas";
    };
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
                inputs = riveInstance.stateMachineInputs(stateMachine);
                // Find the input you want to set a value for, or trigger
                const bumpTrigger = inputs.find(i => i.name === 'bump');
            },    
            
        });

        if (cleanRive) {
            riveInstance.cleanup();
        }
    });
</script>

<canvas id={canvas}></canvas>
