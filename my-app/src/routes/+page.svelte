<script>
    import Header from "../lib/header.svelte";
	import Form from "../lib/form.svelte";
	import Bio from "../lib/bio.svelte";
    import Choice from "../lib/choice.svelte";
</script>

<Header />

<main>
    <section id="section-1">
        <Choice />

    </section>

    <section id="section-2">
        <Bio />
    </section>

    <section id="section-3">
		<Form />
    </section>
</main>

<style>
    section {
        min-height: 100vh;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    #section-1 {
        background: linear-gradient(to bottom, white, lightgray, black);
    }

    #section-2 {
        background: linear-gradient(to bottom, black, lightgray, white);
    }

    h2 {
        font-size: 2rem;
    }
</style>
