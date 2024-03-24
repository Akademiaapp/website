<script>
	import { ArrowDown } from 'lucide-svelte';
</script>

<div class="space-y-8">
	<h1 class="text-7xl font-bold leading-[5rem] max-w-[41rem]">
		<span class="shadow-blue-700">Opgaver</span>,
		<span class="shadow-purple-700">Lektier</span>,
		<span class="shadow-emerald-700">Noter</span>
		- alt samlet i én platform
	</h1>
	<div class="flex gap-10 items-center text-xl">
		<a
			href="https://app.akademia.cc/register"
			class="button shadow primary text-xl px-6 py-1 rounded-md"
		>
			Prøv det!
		</a>
		<a href="" class="fancy flex gap-1 whitespace-nowrap relative items-center">
			Lær mere
			<ArrowDown size="19"></ArrowDown>
		</a>
	</div>
</div>
<img
	src="screenshot.png"
	alt="Screenshot of Akademia"
	class="absolute left-[50rem] h-[25rem] top-[50%] -transform -translate-y-[50%] border rounded-md shadow-lg"
/>

<style lang="scss">
	// span {
	// 	transition: all 300ms;
	// 	position: relative;
	// 	z-index: 1;
	// }

	// span:hover::after {
	// 	transform: scaleX(1);
	// 	transform-origin: left;
	// }
	// span::after {
	// 	content: '';
	// 	position: absolute;
	// 	left: 0;
	// 	z-index: -1;
	// 	transform: scaleX(0);
	// 	transform-origin: right;
	// 	transition: transform 300ms;

	// 	width: 100%;
	// 	bottom: 0.4rem;
	// 	height: 4px;
	// 	background-color: var(--tw-shadow-color);
	// 	// -webkit-text-fill-color: white;
	// 	// -webkit-text-stroke: 1px black;

	// 	// text-shadow: var(--tw-shadow-color) 0 0 10px;
	// }

	.shadow {
		box-shadow: rgb(#000, 0.2) -2px 2px 8px;

		transition: all 0.6s;

		&:not(:active):hover {
			transition: all 0.3s;
			box-shadow: rgb(#000, 0.2) -4px 6px 10px;
			transform: translate(2px, -4px);
		}

		&:active {
			transition: all 0.15s;
		}
	}
</style>
