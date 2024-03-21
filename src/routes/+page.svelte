<script>
	import { ArrowDown } from 'lucide-svelte';
</script>

<div class="header py-40 px-24 space-y-8">
	<h1 class="text-7xl font-bold leading-[5rem] max-w-[40rem]">
		<span class="shadow-blue-700">Opgaver</span>,
		<span class="shadow-purple-700">Lektier</span>,
		<span class="shadow-emerald-700">Noter</span>
		alt samlet i én platform
	</h1>
	<div class="flex gap-10 items-center text-xl">
		<button class="button shadow primary text-xl px-6 py-1 rounded-md"> Prøv det! </button>
		<a href="" class="flex gap-1 whitespace-nowrap relative items-center">
			Lær mere
			<ArrowDown size="19"></ArrowDown>
		</a>
	</div>
</div>

<style lang="scss">
	span {
		transition: all 300ms;
	}
	span:hover {
		// -webkit-text-stroke: 1px black;

		text-shadow: var(--tw-shadow-color) 0 0 10px;
	}
	a {
		&::after {
			content: '';
			display: block;
			width: 100%;
			transform: scaleX(0);
			height: 1px;
			position: absolute;
			background-color: #000;
			transition: transform 0.3s;
			transform-origin: right;
			bottom: 0;
		}

		&:hover::after {
			transform: scaleX(1);
			transform-origin: left;
		}
	}

	.shadow {
		box-shadow: rgb(#000, 0.2) -2px 2px 8px;

		transition: all 0.3s;

		&:hover {
			box-shadow: rgb(#000, 0.2) -4px 6px 10px;
			transform: translate(2px, -4px);
		}
	}
</style>
