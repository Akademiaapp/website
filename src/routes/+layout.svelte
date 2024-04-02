<script lang="ts">
	import DownloadDropdown from './../lib/components/DownloadDropdown.svelte';
	import '../app.scss';
	import { ChevronDown, ExternalLink } from 'lucide-svelte';
	import Footer from '$lib/footer.svelte';
</script>

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
		<a href="/app" class="button hover:bg-muted">Login</a>
		<a href="app/signup" class="button primary">Sign up</a>
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
