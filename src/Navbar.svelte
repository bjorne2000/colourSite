<script>
    import { createEventDispatcher } from 'svelte';
    export let links = [];

    const dispatch = createEventDispatcher();

    function handleClick(event, component) {
        event.preventDefault(); // Prevent the default behavior of the <a> tag
        dispatch('navClick', { component });
    }
</script>

<nav class="navbar">
    <ul>
        {#each links as link}
            <li><a href={link.href} class="nav-link" on:click={(event) => handleClick(event, link.component)}>{link.text}</a></li>
        {/each}
    </ul>
</nav>

<style>
    .navbar {
        width: 100%;
        background-color: #333;
        overflow: hidden;
        position: fixed;
        top: 0;
        left: 0;
        z-index: 1000;
    }

    .navbar ul {
        list-style-type: none;
        margin: 0;
        padding: 0;
        display: flex;
        justify-content: space-around;
    }

    .navbar li {
        display: inline;
    }

    .nav-link {
        display: block;
        color: white;
        text-align: center;
        padding: 14px 20px;
        text-decoration: none;
    }

    .nav-link:hover {
        background-color: #ddd;
        color: black;
    }
</style>