<script lang="ts">
	import '../app.scss';
</script>

<nav>
	<a href="" class="mr-3">
		<img src="akademia-title.svg" alt="" />
	</a>
	<a href="" class="button hover:bg-muted">Download</a>
	<a href="" class="button hover:bg-muted">Lær mere</a>
	<div class="spacer"></div>
	<a href="" class="button hover:bg-muted">login</a>
	<a href="" class="button primary">Sign up</a>
</nav>
<slot />

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

	.button {
		font-size: larger;
		font-weight: 500;
		padding: 0.25rem 0.75rem;
		@apply rounded-md;
		text-align: center;
	}
</style>
