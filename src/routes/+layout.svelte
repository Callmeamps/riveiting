<script>
	// The ordering of these imports is critical to your app working properly
	import '@skeletonlabs/skeleton/themes/theme-crimson.css';
	// If you have source.organizeImports set to true in VSCode, then it will auto change this ordering
	import '@skeletonlabs/skeleton/styles/skeleton.css';
	// Most of your app wide CSS should be put in this file
	import '../app.postcss';
	import { page } from "$app/stores";
	import { AppShell } from '@skeletonlabs/skeleton';
	import SceneToggle from '../lib/canvases/SceneToggle.svelte';


	const toggleCleanRive = (clean) => {
		clean = false;
		if (clean) {
			clean = false;
		}
		else {
			clean = true;
		}
		return clean
	};
	let cleanRive = false;

	let currentPath = $page.url.pathname;

</script>

<AppShell>
	<svelte:fragment slot="header">
		<nav class="flex justify-center w-screen gap-3">
			<a href="/" class="btn btn-icon rounded-md variant-glass-surface">
				<img src="./favicon.png" alt="skull" class="w-5">
				<p class="text-lg">Home</p> 
			</a>
			<a href="/random" class="btn btn-icon rounded-md variant-glass-primary">
				<img src="./favicon.png" alt="skull" class="w-5">
				<p class="text-lg">Random</p> 
			</a>
			<a href="/eye" class="btn btn-icon rounded-md variant-glass-primary">
				<img src="./favicon.png" alt="skull" class="w-5">
				<p class="text-lg">eye</p> 
			</a>
		</nav>
	</svelte:fragment>
	<!-- (sidebarLeft) -->
	<!-- (sidebarRight) -->
	<!-- (pageHeader) -->
	<!-- Router Slot -->
	<div class="h-screen w-screen card variant-ringed-primary flex justify-center border-t-0">
		<slot />
	</div>

	<!-- ---- / ---- -->
	<svelte:fragment slot="pageFooter">Current URL: {$page.url.pathname}</svelte:fragment>
	<!-- (footer) -->
</AppShell>