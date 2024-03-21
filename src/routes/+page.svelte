<script>
</script>

<div class="header py-40 px-24 space-y-8">
	<h1 class="text-7xl font-bold leading-[5rem] max-w-[40rem]">
		Opgaver, Lektier, Noter Alt samlet i én platform
	</h1>
	<div class="flex gap-10 items-center text-xl">
		<button class=" button primary text-xl px-6 py-1 rounded-md"> Prøv det! </button>
		<a href=""> Lær </a>
	</div>
</div>

<style lang="scss">
	a {
		&::after {
			content: '';
			display: block;
			width: 100%;
			transform: scaleX(0);
			height: 1px;
			background-color: #000;
			transition: transform 0.3s;
			transform-origin: right;
		}

		&:hover::after {
			transform: scaleX(1);
			transform-origin: left;
		}
	}
</style>
