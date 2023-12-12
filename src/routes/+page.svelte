
<div class="center">
    <p>
        <img width="150" height="150" src="favicon.png" alt="Logo">
    </p>
    <h1><b>Akademia</b></h1>
    <p>
        A new way of learning, writing and remembering
    </p>
</div>

<div class="buttons">
    <DownloadButton />
    <SeeMoreButton />
</div>

<script lang="ts">
    import DownloadButton from "$lib/components/DownloadButton.svelte";
    import SeeMoreButton from "$lib/components/SeeMoreButton.svelte";
</script>

<style>
    .buttons {
        display: flex;
        justify-content: center;
        gap: 1rem;
    }
</style>
