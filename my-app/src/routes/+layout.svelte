<script>
    import Header from "../lib/header.svelte";
    import Footer from "../lib/footer.svelte";
    import Nav from "../lib/nav.svelte";
    import Loading from "../lib/loading.svelte";
     </script>

<Loading />
<Nav />
<slot />
<Footer />