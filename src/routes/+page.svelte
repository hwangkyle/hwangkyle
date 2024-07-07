<script>
    import { beforeNavigate, goto } from '$app/navigation';

    let inverse = false;

    beforeNavigate(async navigation => {
        // if (closes window || clicks external link) then do nothing
        if (!navigation.to || navigation.to.url.origin !== window.origin)
            return;

        if (!inverse) {
            navigation.cancel();
            inverse = true;
            await new Promise((res,_) => setTimeout(res, 100));
            goto(navigation.to.route.id)
        } else {
            inverse = false;
        }
    })
</script>

<div class:inverse={inverse} id="main">
    
    <div id="left">
        <!-- <a href="/">home</a> -->
        <a href="/experiences">experiences</a>
        <a href="/contact">contact</a>
    </div>

    <div id="line"></div>

    <div id="right">
        <h1>kyle hwang</h1>
        <p>software engineer</p>
    </div>

</div>

<style>
    .inverse, .inverse * {
        color: var(--white);
        background-color: var(--black);
    }
    .inverse #line {
        background-color: var(--white);
    }
    .inverse a:hover {
        text-decoration: underline var(--white) !important;
        text-shadow: 0 0.075em 0.1em var(--light-gray);
    }
    .inverse h1 {
        text-shadow: 0 0.075em 0.1em var(--light-gray);
    }

    #main {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 100vw;
        height: 100vh;
        gap: 5em;
    }

    #left {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: flex-end;
        gap: 1em;
        font-size: 2em;
    }
    #left > a {
        text-decoration: none;
        font-weight: 200;
    }
    #left > a:hover {
        text-decoration: underline var(--black);
        text-shadow: 0 0.075em 0.1em var(--light-gray);
    }

    #line {
        background-color: var(--black);
        height: 30em;
        max-height: 80%;
        width: 1px;
    }
    
    #right {
        display: flex;
        flex-direction: column;
        height: 100%;
        justify-content: center;
        align-items: flex-start;
    }
    #right > h1 {
        font-size: 4.5em;
        font-weight: 500;
        text-shadow: 0 0.075em 0.1em var(--light-gray);
    }
    #right > p {
        font-size: 2em;
        font-weight: 200;
    }
</style>