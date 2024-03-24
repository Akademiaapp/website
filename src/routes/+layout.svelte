<script lang="ts">
	import DownloadDropdown from './../lib/components/DownloadDropdown.svelte';
	import '../app.scss';
	import { ChevronDown, ExternalLink } from 'lucide-svelte';
	import Footer from '$lib/footer.svelte';
</script>

<nav>
	<a href="/" class="mr-3">
		<img src="akademia-title.svg" alt="" />
	</a>
	<DownloadDropdown />
	<a href="#more" class="button hover:bg-muted">Lær mere</a>
	<a href="https://github.com/Akademiaapp" target="_blank" class="button hover:bg-muted">
		Github
		<ExternalLink size="19" />
	</a>
	<div class="spacer"></div>
	<a href="https://app.akademia.cc/" class="button hover:bg-muted">Login</a>
	<a href="https://app.akademia.cc/register" class="button primary">Sign up</a>
</nav>
<div class="min-h-[95vh] max-w-[100rem] mx-auto">
	<div class="py-32 px-10 sm:px-24 flex gap-20 flex-col relative overflow-hidden w-auto">
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
		padding: 0.75rem 2rem;
		gap: 0.7rem;
	}

	nav > :global(*.button) {
		font-size: larger;
		font-weight: 500;
		padding: 0.25rem 0.75rem;
		@apply rounded-md;
		text-align: center;
		@apply flex gap-1.5 items-center;
	}
</style>
