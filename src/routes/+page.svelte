
<div class="center">
    <p>
        <img width="150" height="150" src="favicon.png" alt="Logo">
    </p>
    <h1><b>Akademia</b></h1>
    <p>
        A new way of learning, writing and remembering
    </p>
</div>

<button disabled={!loaded} on:click={window.open(windows_download, '_blank')} >Download windows</button>
<button disabled={!loaded} on:click={window.open(linux_appimage_download, '_blank')} >Download linux appimage</button>
<button disabled={!loaded} on:click={window.open(linux_deb_download, '_blank')} >Download linux deb</button>
<button disabled={!loaded} on:click={window.open(apple_silicon_download, '_blank')} >Download mac silicon</button>
<button disabled={!loaded} on:click={window.open(apple_intel_download, '_blank')} >Download mac intel</button>

<script lang="ts">
    import { onMount } from "svelte";
    var loaded: boolean = false;
    var apple_intel_download: string;
    var apple_silicon_download: string;
    var linux_deb_download: string;
    var linux_appimage_download: string;
    var windows_download: string;

    function download(type: string) {
        window.open(windows_download, '_blank')
    }

    onMount(async () => {
        const base_url = 'https://github.com/Akademiaapp/companion/releases/download/';
        const latest_version = (await (await fetch("https://raw.githubusercontent.com/Akademiaapp/companion/main/package.json")).json())["version"].toLowerCase().replace('v', '');
        windows_download = `${base_url}v${latest_version}/Akademia_${latest_version}_x64_en-US.msi`;
        linux_appimage_download = `${base_url}v${latest_version}/Akademia_${latest_version}_amd64.AppImage`;
        linux_deb_download = `${base_url}v${latest_version}/Akademia_${latest_version}_amd64.deb`;
        apple_silicon_download = `${base_url}v${latest_version}/Akademia_${latest_version}_aarch64.dmg`;
        apple_intel_download = `${base_url}v${latest_version}/Akademia_${latest_version}_aarch6_x64.dmg`;
        loaded = true;
    })
</script>

<style>
    .center {
        align-items: center;
        align-content: center;
    }
</style>
