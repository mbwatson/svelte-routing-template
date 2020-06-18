<script>
    import { fade, fly } from 'svelte/transition'
</script>

<div in:fade={{ duration: 250 }}>
    <div class="side-nav">
        <slot name="sidebar" />
    </div>
    <div class="main-content">
        <slot name="main-content" />
    </div>
</div>

<style>
    div {
        display: flex;
        flex-direction: row;
    }
    .side-nav {
        width: 120px;
        border-right: 1px solid #ccc;
    }
    .main-content {
        flex: 1;
        padding: 0 2rem;
    }
</style>