<script>
	export let heading="Heading"
	export let content="Content"
	import { fade } from 'svelte/transition';
</script>

<main transition:fade>
	<div class="banner text-slate-50">
		<h1 class="text-5xl font-bold">{heading}</h1>
		<content class="text-2xl">{content}</content>
	</div>
</main>

<style>
	:root {
		--theme-gradient: linear-gradient(82.85deg, #aa9fff 0%, #85cfed);
		font-family: Inter;
		font-size: xx-large;
	}

	main {
		/* height: 100vh; */
		display: flex;
		align-items: flex-end;
	}

	.banner {
		display: flex;
		flex-direction: column;
		background-image: var(--theme-gradient);
		width: max-content;
		padding: 1rem;
		padding-left: 2em;
		padding-right: calc(
			1rem + 11vw
		); /* 11vw is height of element, need to figure out how to dynamically find element height via css */
		text-shadow: 0px 4px 23px rgba(0, 0, 0, 0.5);
		clip-path: polygon(
			0% 0%,
			0% 100%,
			100% 100%,
			calc(100% - 11vw) 0% /* see above for spec re: 11vw */
		);
	}
</style>
