<script>
	import { Badge } from '$lib/components/ui/badge';
	import ContactForm from '$lib/contactForm.svelte';
	import { ArrowDown } from 'lucide-svelte';
</script>

<div
	class="hero relative py-12 min-h-[calc(90vh-5rem)] sm:h-[calc(90vh-15rem)] sm:min-h-[20rem] px-8 w-full my-5 sm:px-24 grid place-items-center"
>
	<div class="w-full">
		<div class="space-y-8 relative m-auto max-w-[90rem]">
			<Badge class="text-lg">Beta</Badge>
			<h1
				class="text-center sm:text-left text-[2.5rem] sm:text-6xl md:text-7xl font-bold leading-[1.2em] max-w-[41rem]"
			>
				<span class="">Opgaver</span>,
				<span class="">Lektier</span>,
				<span class="">Noter</span>
				- alt samlet i én platform
			</h1>
			<img
				src="screenshot.png"
				alt="Screenshot of Akademia"
				class="mb-auto border rounded-md shadow-lg sm:hidden"
			/>
			<div class="flex gap-10 justify-center sm:justify-start items-center text-xl">
				<a
					href="/app/signup"
					class="button hidden sm:block shadow primary text-xl px-6 py-1.5 rounded-md"
				>
					Prøv det!
				</a>
				<a href="#more" class="fancy flex gap-1 whitespace-nowrap relative items-center">
					Lær mere
					<ArrowDown size="19"></ArrowDown>
				</a>
			</div>
			<img
				src="screenshot.png"
				alt="Screenshot of Akademia"
				class="absolute left-[45rem] h-[25rem] top-[40%] -transform -translate-y-[50%] border rounded-md shadow-lg"
			/>
		</div>
	</div>
</div>

<div class=" py-24 px-6 sm:px-36 border-t border-b text-center bg-white" id="more">
	<div class="mx-auto flex flex-col items-center max-w-[90rem]">
		<h1 class="text-5xl sm:text-6xl font-bold leading-[1.2em]">Revolutionér din skoledag</h1>
		<p class="text-center max-w-[60rem] text-xl mt-5 font-normal text-muted-foreground">
			Akademia er ikke bare endnu en platform - det er din ultimative løsning til at forenkle din
			skoledag. Forestil dig en verden, hvor alt hvad du behøver, fra opgaver og lektier til dine
			vigtigste noter, er samlet ét sted.
		</p>
		<div class="grid grid-cols-1 lg:grid-cols-2 xl:grid-cols-3 gap-4 w-full mt-6 text-left">
			<div class="p-4">
				<h2 class="text-xl font-bold">Dashboard</h2>
				<p class="text-muted-foreground">
					Få et hurtigt overblik over dine opgaver, lektier og noter med Akademias dashboard. Med et
					enkelt klik kan du se, hvad du skal lave, og hvad du har lavet.
				</p>
			</div>
			<div class="p-4">
				<h2 class="text-xl font-bold">Fil-lagring</h2>
				<p class="text-muted-foreground">
					Slut med at du ikke kan finde dine filer! Akademia gør det let at gemme dine filer, og
					hurtigt at finde den igen. Derudover det sørger Akademia for at dine dokumenter og noter
					altid er gemt, så du ikke taber dit arbejde.
				</p>
			</div>
			<div class="p-4">
				<h2 class="text-xl font-bold">Kalender</h2>
				<p class="text-muted-foreground">
					Få et hurtigt overblik over din dag, og planlæg dine aktiviteter effektivt med vores
					integrerede kalenderfunktion.
				</p>
			</div>
			<div class="p-4">
				<h2 class="text-xl font-bold">Samarbejde i Real-time</h2>
				<p class="text-muted-foreground">
					Samarbejd hurtigt og nemt med dine med-elever med Akademias real-time samarbejdsværktøjer.
					Del idéer og rediger dokumenter sammen uden forsinkelser. Med Akademia bliver teamwork en
					leg!
				</p>
			</div>
			<div class="p-4">
				<h2 class="text-xl font-bold">Gør det dit eget</h2>
				<p class="text-muted-foreground">
					Hver af os er unikke med vores egne sæt behov og præferencer. Derfor giver Akademia dig
					mulighed for at tilpasse platformen præcis efter dine ønsker og behov.
				</p>
			</div>
			<div class="p-4">
				<h2 class="text-xl font-bold">Indbygget editor</h2>
				<p class="text-muted-foreground">
					Rediger dine dokumenter direkte i Akademia med vores indbyggede editor. Akademias editor
					simplificerer ikke kun din arbejdsprocess, men gør det også drastisk hurtigere at åbne
					dokumenter.
				</p>
			</div>
		</div>
	</div>
</div>
<div class="mx-auto">
	<div
		class="flex -mx-5 justify-center flex-col lg:flex-row max-w-[110rem] px-6 sm:px-36 lg:gap-12"
	>
		<div class="right-0 top-0 flex-1 rounded-xl p-10 gap-3 flex flex-col">
			<h2 class="text-4xl font-semibold">Om os</h2>
			<p>
				Vi er to unge udviklere som selv er opvokset med et skolesystem, som vi mener kan og skal
				forbedres. En af de ting som skabte de største frustrationer for os, vores medelever og
				undervisere, var hvordan de nuværende platforme håndterer opgaver og lektier. Det var altid
				en lang og kompliceret process bare for at åbne en opave. Derfor har vi skabt Akademia, som
				er en platform, der er skabt til at gøre din skoledag så nem og effektiv som muligt.
			</p>
			<img src="team.jpg" alt="Team" class="rounded-lg shadow-lg" />
		</div>
		<div class="border-l" />
		<ContactForm />
	</div>
	<div class="h-5 sm:h-0"></div>
</div>

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
