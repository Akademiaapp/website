<script lang="ts">
	import DownloadDropdown from './../lib/components/DownloadDropdown.svelte';
	import '../app.scss';
	import { ChevronDown, ExternalLink } from 'lucide-svelte';
</script>

<nav>
	<a href="" class="mr-3">
		<img src="akademia-title.svg" alt="" />
	</a>
	<DownloadDropdown />
	<a href="" class="button hover:bg-muted">Lær mere</a>
	<a href="https://github.com/Akademiaapp" target="_blank" class="button hover:bg-muted">
		Github
		<ExternalLink size="19" />
	</a>
	<div class="spacer"></div>
	<a href="https://app.akademia.cc/" class="button hover:bg-muted">Login</a>
	<a href="https://app.akademia.cc/register" class="button primary">Sign up</a>
</nav>
<div class="header py-32 px-24 flex gap-20 relative overflow-hidden w-auto max-w-[100rem] mx-auto">
	<slot />
</div>

<style lang="scss">
	a,
	button > :global(svg) {
		transform: translateY(0.1rem);
	}

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
