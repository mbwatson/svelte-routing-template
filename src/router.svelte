<script>
    import { Route } from 'svelte-routing'
    
    import Home from './pages/home.svelte'
    import About from './pages/about.svelte'
    import Contact from './pages/contact.svelte'
</script>

<Route path="/" component={Home} />
<Route path="/about" component={About} />
<Route path="/contact" component={Contact} />
