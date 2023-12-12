<button class="mainbutton">
    <a href="#more">See more</a>
</button>


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
        min-width: max-content;
        user-select: none;
        color: black;
        font-weight: 600;
        font-size: 1rem;
        font-family: 'Roboto', sans-serif;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    a:hover {
		filter: brightness(85%);
	}

    .mainbutton:hover {
        filter: brightness(85%);
    }

    .mainbutton:active {
        filter: brightness(70%);
    }

    .mainbutton {
        display: flex;
        align-items: center;
        gap: 0.5rem;
        padding: 0.5rem;
        border-radius: 10px;
        background-color: #56C7E0;
        border-radius: 100px;
        padding-left: 1rem;
        padding-right: 1rem;
        text-decoration: none;
    }
</style>