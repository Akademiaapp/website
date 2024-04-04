<script>
	import { goto } from '$app/navigation';
	import { page } from '$app/stores';
	import { onMount } from 'svelte';

	let state = 'loading';

	onMount(async () => {
		try {
			const response = await fetch(
				'https://api.akademia.cc/public/schools/0aad6f5f-3f49-41a4-8b1e-19780ddd6774/groups'
			);
			const data = await response.json();
			state = 'loaded';
			console.log($page.url.pathname);
			if ($page.url.pathname === '/app/signup') {
				goto('https://app.akademia.cc/register');
			} else {
				goto('https://app.akademia.cc');
			}
		} catch (error) {
			state = 'error';
			console.error(error);
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
