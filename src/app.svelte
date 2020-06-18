<script>
    import { Router, Route } from 'svelte-routing'
    import NavLink from './components/navlink.svelte'
    export let url = ''
    
    import Header from './components/layout/header.svelte'
    import Menu from './components/menu.svelte'
    import Main from './components/layout/main.svelte'
    import Footer from './components/layout/footer.svelte'
    
    import Home from './pages/home.svelte'
    import About from './pages/about.svelte'
    import Contact from './pages/contact.svelte'
</script>

<Header>
    <Router url={url}>
        <NavLink to="/">SITE TITLE</NavLink>
        <Menu>
            <NavLink to="/about">About</NavLink>
            <NavLink to="/contact">Contact</NavLink>
        </Menu>
    </Router>
</Header>
<Main>
    <Router url={url}>
        <div>
            <Route path="/" component={Home} />
            <Route path="/about" component={About} />
            <Route path="/contact" component={Contact} />
        </div>
    </Router>
</Main>
<Footer>
    &copy; {(new Date()).getFullYear()}
</Footer>

<style>
	h1 {
		color: purple;
	}
</style>
