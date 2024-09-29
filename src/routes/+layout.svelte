<script lang="ts">
	import DownloadDropdown from './../lib/components/DownloadDropdown.svelte';
	import '../app.scss';
	import { X, ExternalLink } from 'lucide-svelte';
	import Footer from '$lib/footer.svelte';
	import { onMount } from 'svelte';
	import { goto } from '$app/navigation';
	import { fly } from 'svelte/transition';

	let showBetaWarning = true;

	onMount(async () => {
		try {
			const response = await fetch('https://api.akademia.cc/public/schools');
			const data = await response.json();
			goto('https://akademia.cc/');
		} catch (error) {}
	});

	function beforeOpen() {
		alert('Du er ved at åbne en beta version af Akademia');
	}
</script>

{#if showBetaWarning}
<header class="w-full p-5 px-9 bg-yellow-300 flex justify-between" transition:fly={{ y: -100 }}>
	<b>⚠️ OBS. AKADEMIA ER STADIG I EN MEGET TIDLIG STADIE. 🚧</b>
	<div class="flex gap-5">
		<b>⚠️ ATTENTION. AKADEMIA IS STILL IN A VERY EARLY STAGE. 🚧</b>
		<button on:click={() => showBetaWarning = false}>
			<X size="24" />
		</button>
	</div>
</header>
{/if}

<nav class="px-3 md:px-8 py-3">
	<a href="/" class="mr-3">
		<img src="/akademia-title.svg" alt="" />
	</a>
	<div class="hidden md:flex w-full gap-2">
		<DownloadDropdown />
		<a href="#more" class="button hover:bg-muted">Lær mere</a>
		<a href="https://github.com/Akademiaapp" target="_blank" class="button hover:bg-muted">
			Github
			<ExternalLink size="19" />
		</a>
		<div class="spacer"></div>
		<a href="https://app.akademia.cc" class="button hover:bg-muted" on:click={beforeOpen}>Login</a>
		<a href="https://app.akademia.cc/register" class="button primary" on:click={beforeOpen}>Sign up</a>
	</div>
</nav>
<div class="min-h-[95vh] mx-auto">
	<div class="sm:py-12 flex sm:gap-20 flex-col mx-auto relative overflow-hidden w-auto">
		<slot />
	</div>
</div>

<Footer />

<style lang="scss">
	img {
		/* width: 100%; */
		height: 3rem;
	}

	.spacer {
		flex: 1;
	}

	nav {
		display: flex;

		align-items: center;

		gap: 0.7rem;
	}

	nav > * :global(*.button),
	nav > :global(*.button) {
		font-size: larger;
		font-weight: 500;
		padding: 0.25rem 0.75rem;
		@apply rounded-md;
		text-align: center;
		@apply flex gap-1.5 items-center;
	}
</style>
