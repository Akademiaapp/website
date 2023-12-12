<script lang="ts">
    import { onMount } from "svelte";

    interface platform {
        name: string,
        os_name: string;
        ending: string,
        download_url?: string
    }

    let dropdown_open: boolean = false;

    var loading: boolean = true;
    const base_url = 'https://github.com/Akademiaapp/companion/releases/download/';

    let platforms: platform[] = 
    [{
        name: 'Linux Appimage',
        ending: '_amd64.AppImage',
        os_name: 'MacIntel'
    }, {
        name: 'Linux Deb',
        ending: '_amd64.deb',
        os_name: 'Linux x86_64'
    }, {
        name: 'Mac Silicon',
        ending: '_aarch64.dmg',
        os_name: 'MacIntel'
    }, {
        name: 'Mac Intel',
        ending: '_aarch6_x64.dmg',
        os_name: 'MacIntel'
    }, {
        name: 'Windows',
        ending: '_x64_en-US.msi',
        os_name: 'Win32'
    }]

    onMount(async () => {
        const latest_version = (await (await fetch("https://raw.githubusercontent.com/Akademiaapp/companion/main/package.json")).json())["version"].toLowerCase().replace('v', '');
        const current_platform = window.navigator.platform;
        platforms.forEach(platform => {
            platform.download_url = `${base_url}v${latest_version}/Akademia_${latest_version}${platform.ending}`;
        });
        console.log(platforms)
        // Put the current platform at the top
        platforms.sort((a, b) => {
            if (a.os_name == current_platform) return -1;
            if (b.os_name == current_platform) return 1;
            return 0;
        });
        console.log(platforms)
        platforms = platforms;
        loading = false;
    })
</script>


<div class="dropdown_container" >
    <div class="button_container">
        <button class="mainbutton" on:click disabled={loading}>
            <a href={platforms[0].download_url}><img src="/icons/download.svg" alt="Download {platforms[0].name}" />Download {platforms[0].name}</a>
        </button>
        <button class="dropdown_button" on:click={e => dropdown_open = !dropdown_open} disabled={loading}>
            <img class={dropdown_open ? 'dropdown_image rotate' : 'dropdown_image'} src="/icons/arrow.svg" alt="Download" />
        </button>
    </div>
        
    {#if dropdown_open}
        <div class="dropdown">
            <!-- Hide the first platform -->
            {#each platforms.slice(1) as platform}
                <button>
                    <a class="dropdown_element" href={platform.download_url}><img src="/icons/download.svg" alt="Download {platform.name}" />Download {platform.name}</a>   
                </button>
            {/each}
        </div>
    {/if}
</div>

<style>
	button {
        border: none;
		background-color: transparent;
		padding: 0;
		margin: 0;
	}
    a {
        font-size: 0.95rem;
        text-decoration: none;
        gap: 0.5rem;
        cursor: pointer;
        justify-content: center;
        border: none;
		border-radius: 100px;
        min-width: max-content;
        user-select: none;
        color: black;
        font-weight: 600;
        font-size: 1rem;
        font-family: 'Roboto', sans-serif;
        display: flex;
        justify-content: center;
        align-items: center;
        margin-top: 0.5rem;
        margin-bottom: 0.5rem;
    }
    a:hover {
		filter: brightness(85%);
	}
    img {
		height: 20px;
	}

    .dropdown_container {
        position: relative;
    }

    .dropdown {
        position: absolute;
        top: 100%;
        left: 0;
        margin-top: 0;
        background-color: #4EB0C6;
        border-radius: 10px;
        padding: 0.5rem;
        display: flex;
        flex-direction: column;
        gap: 0.5rem;
    }

    .dropdown_element {
        display: flex;
        align-items: center;
        gap: 0.5rem;
        padding: 0.5rem;
        border-radius: 10px;
        background-color: 4EB0C6;
        text-decoration: none;
    }

    .dropdown_element:hover {
        filter: brightness(85%);
    }

    .dropdown_button {
        border-radius: 100px;
        display: flex;
        align-items: center;
        gap: 0.5rem;
        padding: 0.5rem;
        border-radius: 100px;
        background-color: #4EB0C6;
        text-decoration: none;
        padding-right: 0.8rem;
        border-top-left-radius: 0;
        border-bottom-left-radius: 0;
    }

    .dropdown_button:hover {
        filter: brightness(85%);
    }

    .mainbutton:hover {
        filter: brightness(85%);
    }

    .mainbutton:active {
        filter: brightness(70%);
    }

    .dropdown_button:active {
        filter: brightness(70%);
    }

    .dropdown_image {
        height: 20px;
        transform: rotate(90deg);
        transition: transform 0.3s ease;
    }

    .rotate {
        transform: rotate(0deg);
    }

    .mainbutton {
        display: flex;
        align-items: center;
        gap: 0.5rem;
        padding: 0.5rem;
        border-radius: 100px;
        background-color: #4EB0C6;
        text-decoration: none;
        border-top-right-radius: 0;
        border-bottom-right-radius: 0;
        padding-left: 1rem;
        padding-right: 1rem;
    }

    .button_container {
        display: flex;
    }

</style>