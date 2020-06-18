<header>
    <slot />
</header>

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
</style>
