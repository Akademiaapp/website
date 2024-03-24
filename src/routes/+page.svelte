<script>
	import ContactForm from '$lib/contactForm.svelte';
	import { ArrowDown } from 'lucide-svelte';
</script>

<div class="hero relative">
	<div class="space-y-8">
		<h1
			class="text-center sm:text-left text-7xl md:text-7xl font-bold leading-[1.2em] max-w-[41rem]"
		>
			<span class="shadow-blue-700">Opgaver</span>,
			<span class="shadow-purple-700">Lektier</span>,
			<span class="shadow-emerald-700">Noter</span>
			- alt samlet i én platform
		</h1>
		<div class="flex gap-10 justify-center sm:justify-start items-center text-xl">
			<a
				href="https://app.akademia.cc/register"
				class="button shadow primary text-xl px-6 py-1.5 rounded-md"
			>
				Prøv det!
			</a>
			<a href="#more" class="fancy flex gap-1 whitespace-nowrap relative items-center">
				Lær mere
				<ArrowDown size="19"></ArrowDown>
			</a>
		</div>
	</div>
	<img
		src="screenshot.png"
		alt="Screenshot of Akademia"
		class="absolute left-[45rem] h-[25rem] top-[50%] -transform -translate-y-[50%] border rounded-md shadow-lg"
	/>
</div>

<div class="mt-36 px-10 flex flex-col items-center text-center">
	<h1 class="text-6xl font-bold leading-[1.2em]" id="more">Hurtigere arbejdsprocess</h1>
	<p class="text-center max-w-[60rem] text-2xl mt-5 font-normal text-muted-foreground">
		Akademia er ikke bare endnu en platform - det er din ultimative løsning til at forenkle din
		skole hverdag. Forestil dig en verden, hvor alt hvad du behøver, fra opgaver og lektier til dine
		vigtigste noter, er samlet ét sted.
	</p>

	<div class="grid grid-cols-1 lg:grid-cols-2 xl:grid-cols-3 gap-4 w-full mt-5 text-left">
		<div class="p-4">
			<h2 class="text-lg font-bold">Item 1</h2>
			<p class="text-muted-foreground">Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
		</div>
		<div class="p-4">
			<h2 class="text-lg font-bold">Filstrukturering</h2>
			<p class="text-muted-foreground">
				Slut med at du ikke kan finde dine filer! Akademia gør det let at gemme dine filer, og
				hurtigt at finde den igen.
			</p>
		</div>
		<div class="p-4">
			<h2 class="text-lg font-bold">Kalender</h2>
			<p class="text-muted-foreground"></p>
			<p class="text-muted-foreground">
				Få et hurtigt overblik over din dag, og planlæg dine aktiviteter effektivt med vores
				integrerede kalenderfunktion.
			</p>
		</div>
		<div class="p-4">
			<h2 class="text-lg font-bold">Collaboration i Real-time</h2>
			<p class="text-muted-foreground">
				Samarbejd gnidningsløst med dine med-elever med Akademias real-time samarbejdsværktøjer. Del
				idéer og rediger dokumenter sammen uden forsinkelser. Med Akademia bliver teamwork en leg!
			</p>
		</div>
		<div class="p-4">
			<h2 class="text-lg font-bold">Item 1</h2>
			<p class="text-muted-foreground">Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
		</div>
		<div class="p-4">
			<h2 class="text-lg font-bold">Item 1</h2>
			<p class="text-muted-foreground">Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
		</div>
	</div>
	<img
		src="screenshot.png"
		alt="Screenshot of Akademia"
		class="h-[25rem] ml-10 border rounded-md shadow-lg"
	/>
</div>

<ContactForm />

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
