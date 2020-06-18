<script>
    import { Router } from 'svelte-routing'
    import PageRouter from './router.svelte'
    import NavLink from './components/navlink.svelte'
    export let url = ''
    
    import Menu from './components/menu.svelte'
    
</script>

<Router url={url}>
    <header>
        <NavLink to="/">SITE TITLE</NavLink>
        <Menu>
            <NavLink to="/about">About</NavLink>
            <NavLink to="/contact">Contact</NavLink>
        </Menu>
    </header>
    <main>
        <PageRouter url={url}/>
    </main>
    <footer>
        &copy; {(new Date()).getFullYear()}
    </footer>
</Router>


<style>
    header {
        position: sticky;
        top: 0;
        background-color: #333;
        filter: drop-shadow(0 0 0.25rem #00000099);
        display: flex;
        flex-direction: row;
        justify-content: space-between;
    }
    main {
        display: flex;
    }
    footer {
        filter: drop-shadow(0 0 0.25rem #00000099);
        background-color: #333;
        padding: 1rem;
        color: #eee;
    }
</style>