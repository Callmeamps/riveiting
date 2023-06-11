<script>
import onMount from "svelte";
import rive from "@rive-app/canvas";


onMount(() => {
	const rivCanvas = document.getElementById("rive");
	let mainCard = document.getElementByClass("card");
	let r = new rive({
		src: "./reach.riv",
		autoplay: true,
		artboard: "reach",
		stateMachine: "PullDown",
		canvas: rivCanvas,
		onLoad: () => {
			r.resizeDrawingSurfaceToCanvas();
		},
	});
});
</script>
<div class="card">
	<canvas id="rive"></canvas>
</div>