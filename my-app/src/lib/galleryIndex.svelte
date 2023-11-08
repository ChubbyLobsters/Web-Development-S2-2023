<script>
    import { onMount } from 'svelte';

    export let images = [];
    export let altText = 'images for gallery';

    // Function to preload images
    async function preloadImages(images) {
        for (const image of images) {
            const imgElement = new Image();
            imgElement.src = image;
            await new Promise((resolve) => {
                imgElement.onload = resolve;
            });
        }
    }

    onMount(() => {
        preloadImages(images);
    });
</script>

<style>
    .gallery {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        gap: 10px;
        padding: 0 35px;
    }

    .gallery img {
        width: 30%; /* fixed width for all images */
        height: auto; /* Maintain aspect ratio */
        object-fit: cover; /* Crop images to fit within their fixed dimensions */
    }
</style>

<div class="gallery">
    {#each images as image (image)}
        <img src={image} alt={altText} />
    {/each}
</div>
