<script>
    import { fade, fly } from 'svelte/transition'
    let sidebarOpen = true
    const toggleSidebarVisibility = event => sidebarOpen = !sidebarOpen
</script>

<div in:fade={{ duration: 250 }} class:sidebar-open={sidebarOpen}>
    <div class="sidebar">
        <nav>
            <slot name="sidebar" />
        </nav>
    </div>
    <button class="sidebar-toggler" on:click={toggleSidebarVisibility}>
        <span>{#if sidebarOpen}close menu{:else}open menu{/if}</span>
    </button>
    <div class="main-content">
        <slot name="main-content" />
    </div>
</div>

<style>
    div {
        display: flex;
        flex-direction: row;
        position: relative;
    }
    .sidebar-toggler {
        background-color: #fff;
        filter: brightness(0.95);
        transition: filter 250ms;
        color: #999;
        border: none;
        border-right: 1px solid #ddd;
        border-left: 1px solid #ddd;
        cursor: pointer;
        font-size: 75%;
        writing-mode: sideways-lr;
        text-orientation: sideways;
        font-weight: normal;
        padding: 0;
    }
    .sidebar-toggler:hover {
        filter: brightness(0.9);
    }
    .sidebar-toggler span {
        opacity: 0.3;
        transition: opacity 1000ms;
    }
    .sidebar-toggler:hover span {
        transition: opacity 250ms;
        opacity: 1.0;
    }
    .sidebar {
        width: 240px;
        max-width: 0;
        transition: max-width 250ms;
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: stretch;
    }
    .sidebar-open .sidebar {
        max-width: 240px;
    }
    nav {
        flex: 1;
        width: 240px;
        position: absolute;
        top: 0;
        right: 0;
        padding: 1rem;
    }
    .main-content {
        flex: 1;
        padding: 0 2rem;
    }
</style>