<svelte:head>
    <title>Kyle Hwang</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap" rel="stylesheet">
</svelte:head>

<slot />

<style>
    :global(*) {
        --header-height: 20px;
        --black: #333333;
        --dark-gray: #555555;
        --gray:  #888888;
        --light-gray: #a8a8a8;
        --lighter-gray: #bbbbbb;
        --white: #e8e8e8;

        background-color: var(--white);
        color: var(--black);

        font-family: "Poppins", sans-serif;

        margin: 0;
        padding: 0;
    }
    :global(a:visited) {
        color: var(--black);
    }

    /* header {
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 1em;
        height: var(--header-height);
    }
    main {
        height: calc(100vh - var(--header-height));
    } */
</style>