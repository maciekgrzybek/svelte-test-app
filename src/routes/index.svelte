<script>
	import { inview } from 'svelte-inview';

	let isInView;
	const options = { unobserveOnEnter: false };
</script>

<main>
	<p>
		Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte
		apps.
	</p>
</main>

<div use:inview={options} on:inviewChange={({ detail: { inView } }) => (isInView = inView)} on>
	{#if isInView}
		Stuff here...
	{/if}
</div>

<style>
	main {
		height: 1200px;
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>
