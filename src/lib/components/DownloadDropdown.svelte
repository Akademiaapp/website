<script lang="ts">
	import { ChevronDown } from 'lucide-svelte';

	import { onMount } from 'svelte';

	interface platform {
		name: string;
		os_name: string;
		ending: string;
		download_url?: string;
	}

	let dropdown_open: boolean = false;

	var loading: boolean = true;
	const base_url = 'https://github.com/Akademiaapp/companion/releases/download/';

	let platforms: platform[] = [
		{
			name: 'Linux Appimage',
			ending: '_amd64.AppImage',
			os_name: 'Linux x86_64'
		},
		{
			name: 'Linux Deb',
			ending: '_amd64.deb',
			os_name: 'Linux x86_64'
		},
		{
			name: 'Mac Silicon',
			ending: '_aarch64.dmg',
			os_name: 'MacIntel'
		},
		{
			name: 'Mac Intel',
			ending: '_x64.dmg',
			os_name: 'MacIntel'
		},
		{
			name: 'Windows',
			ending: '_x64-setup.exe',
			os_name: 'Win32'
		}
	];

	onMount(async () => {
		const latest_version = (
			await (
				await fetch('https://raw.githubusercontent.com/Akademiaapp/companion/main/package.json')
			).json()
		)['version']
			.toLowerCase()
			.replace('v', '');
		const current_platform = window.navigator.platform;
		platforms.forEach((platform) => {
			platform.download_url = `${base_url}v${latest_version}/Akademia_${latest_version}${platform.ending}`;
		});
		// Put the current platform at the top
		platforms.sort((a, b) => {
			if (a.os_name == current_platform) return -1;
			if (b.os_name == current_platform) return 1;
			return 0;
		});
		platforms = platforms;
		loading = false;
	});
</script>

<button class="button hover:bg-muted dropdown"
	>Download
	<ChevronDown size="15" />
	<div class="border">
		{#each platforms as platform}
			<a class="hover:bg-muted" href={platform.download_url} download>{platform.name}</a>
		{/each}
	</div>
</button>

<style>
</style>
