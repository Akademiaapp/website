<script>
	import { goto } from '$app/navigation';
	import { page } from '$app/stores';
	import { onMount } from 'svelte';

	let state = 'loading';

	onMount(async () => {
		try {
			const response = await fetch(
				'https://api.akademia.cc/public/schools'
			);
			const data = await response.json();
			state = 'loaded';
			if ($page.url.pathname.includes('signup')) {
				goto('https://app.akademia.cc/register');
			} else {
				goto('https://app.akademia.cc');
			}
		} catch (error) {
			try {
				const response = await fetch(
					'https://akademia-api.arctix.dev/public/schools'
				);
				const data = await response.json();
				state = 'loaded';
				console.log($page.url.pathname);
				if ($page.url.pathname === '/app/signup') {
					goto('https://akademia-webapp.arctix.dev/register');
				} else {
					goto('https://akademia-webapp.arctix.dev/');
				}
			} catch (error) {
				state = 'error';
				console.error(error);
			}
		}
	});
</script>

<div class="grid h-[calc(100vh-15rem)] w-full place-items-center">
	{#if state === 'loading'}
		<p class="text-xl">Loading...</p>
	{:else if state === 'error'}
		<p class="text-xl">
			Du har desværre ikke adgang til Akademia. Vi arbejder på at få dette fikset hurtigst muligt.
		</p>
	{/if}
	<slot />
</div>
