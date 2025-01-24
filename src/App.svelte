<script>
    import StartPage from "./StartPage.svelte";
    import Navbar from "./Navbar.svelte";
    import Swirl from "./Swirl.svelte";

    let links = [
        { href: '#', text: 'StartPage', component: StartPage },
        { href: '#', text: 'Swirl', component: Swirl },
        { href: '#', text: 'pinne', component: null } // Add your Pinne component here if needed
    ];
    let currentComponent = StartPage;

function handleNavClick(event) {
    currentComponent = event.detail.component;
}

</script>

<Navbar {links} on:navClick={handleNavClick} />
<main class="global">
   
    {#if currentComponent}
        <svelte:component this={currentComponent} />
    {/if}
    
       
        
    
    
</main>

<style>
    main {
        display: flex;
    }
    .global{
        display: flex;
    }

</style>