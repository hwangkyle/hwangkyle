<script>
    import { inverse } from '$lib/stores.js';
</script>

<div class:inverse={$inverse} id="menu">
    <a href="/">home</a>
    <a href="/experiences">experiences</a>
    <a href="/contact">contact</a>
</div>

<div class:inverse={$inverse} id="line"></div>

<style>
    #menu {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: flex-end;
        gap: 1em;
        font-size: 2em;
    }
    #menu > a {
        text-decoration: none;
        font-weight: 200;
    }
    #menu > a:hover {
        text-decoration: underline var(--black);
        text-shadow: 0 0.075em 0.1em var(--light-gray);
    }

    #line {
        background-color: var(--black);
        height: 30em;
        max-height: 80%;
        width: 1px;
    }
    
    .inverse#line {
        background-color: var(--white);
    }
    .inverse > a:hover {
        text-decoration: underline var(--white) !important;
        text-shadow: 0 0.075em 0.1em var(--light-gray);
    }
</style>