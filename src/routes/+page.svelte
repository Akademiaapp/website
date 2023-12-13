
<div class="hero">
    <p class="logo">
        <img width="150" height="150" src="favicon.png" alt="Logo">
    </p>
    <h1 class="title">Akademia</h1>
    <p class="subtitle">
        A new way of learning, writing and remembering
    </p>
    <div class="buttons">
        <DownloadButton />
        <SeeMoreButton />
    </div>
</div>


<script lang="ts">
    import DownloadButton from "$lib/components/DownloadButton.svelte";
    import SeeMoreButton from "$lib/components/SeeMoreButton.svelte";
</script>

<style>
    .title {
        margin-bottom: 0;
    }

    .subtitle {
        margin-top: 0;
        font-size: 1.5rem;
        font-weight: 400;
    }

    .logo {
        display: flex;
        justify-content: center;
        align-items: center;
        margin-top: 8rem;
    }

    * {
        font-family: "Manrope", sans-serif;
    }

    .buttons {
        display: flex;
        justify-content: center;
        gap: 1rem;
    }

    .hero {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 1rem;
    }
</style>
