<script>
    import Header from "$lib/components/Header.svelte";
    import Footer from "$lib/components/Footer.svelte";
</script>

<style>
    @font-face {
        font-family:'Noto Sans', sans-serif;
        font-style:normal;
        font-weight: 400;
        src: url("https://fonts.googleapis.com/css2?family=Noto+Sans:ital,wght@0,200;0,300;0,400;0,700;1,200;1,500&display=swap");
    }
    main {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        font-family: "Noto Sans", sans-serif;
    }
    main > * {
        margin: auto;
        width: 85vw;
        height: min-content;
    }
</style>

<main>
    <Header/>
    <section>
	    <slot />
    </section>
    <Footer/>
</main>