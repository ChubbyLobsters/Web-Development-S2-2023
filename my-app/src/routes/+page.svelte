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
    main {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }

    section {
        flex: 1;
        display: flex;
        align-items: center;
        justify-content: center;
        max-height: 140vh; /* Set a maximum height for sections */
        max-width: 80%;
        min-height: auto; /* Remove the fixed minimum height */
        position: relative;
        margin: 10px 0; /* Add margin for spacing between sections */
    }

  

    @media screen and (max-width: 2560px) {
        section {
            max-height: 140vh; /* Reduce the maximum height for smaller screens */
            padding: 20px; /* Add padding for spacing */
            margin: 10% 0; /* Adjust margin for spacing between sections */
        }
    }

    @media screen and (max-width: 768px) {
        section {
            max-height: 100vh; /* Reduce the maximum height for smaller screens */
            padding: 20px; /* Add padding for spacing */
            margin: 20px 0; /* Adjust margin for spacing between sections */
        }
    }

    @media screen and (max-width: 480px) {
        section {
            max-height: 80vh; /* Further reduce the maximum height for smaller screens */
            margin: 20px 0; /* Adjust margin for spacing between sections */
        }
    }

    @media screen and (max-width: 425px) {
        section {
            max-height: 60vh; /* Further reduce the maximum height for smaller screens */
            margin: 20px 0; /* Adjust margin for spacing between sections */
        }
    }

    @media screen and (max-width: 375px) {
        section {
            max-height: 40vh; /* Further reduce the maximum height for smaller screens */
            margin: 20px 0; /* Adjust margin for spacing between sections */
        }
    }

    @media screen and (max-width: 320px) {
        section {
            max-height: 20vh; /* Further reduce the maximum height for smaller screens */
            margin: 20px 0; /* Adjust margin for spacing between sections */
        }
    }
</style>
