<script>
    import Nav from "../lib/nav.svelte";
    import Loading from "../lib/loading.svelte";
  
    let isLoading = true;
  
    // Simulate loading for demonstration purposes
    setTimeout(() => {
      isLoading = false;
    }, 4000);
  </script>
  
  {#if isLoading}
    <Loading />
  {/if}
  
  <Nav />
  <main>
    <slot />
  </main>
  
  <style>
  </style>
  