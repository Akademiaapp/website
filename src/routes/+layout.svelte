<script lang="ts">
	import '../app.scss';
</script>

<nav>
	<img src="akademia-title.svg" alt="" />
	<a href="">Download</a>
	<div class="spacer"></div>
</nav>
<slot />

<style>
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
		padding: 0.75rem 0.8rem;
		gap: 0.5rem;
	}
</style>
