<script>
    let bio = "In the world of artistry, we, the craftsmen, doth aspire to sway the belief that Forgotten Dreams should ne'er be cast into the abyss of oblivion; instead, they should be enshrined in memory's keep. Through our chosen medium, we labor to breathe life into the ethereal realms of our innermost thoughts, where dreams, once vivid and poignant, may have waned into shadow. We hold it true that within these forsaken dreams doth lie untapped wellsprings of inspiration, nostalgia, and untold tales, awaiting reawakening. As artists, we bear the torch of history, rekindling the embers of dreams neglected, to set the minds of today ablaze, ensuring their grace and significance persist, refusing to wither into the forgotten corners of time. And thus, we must delve deep into the recesses of our souls, summoning forth the creepy and the bizarre, for it is in the strangest and most unsettling of dreams that the truest expressions of art may be found. In embracing the eerie and the uncanny, we unearth the hidden treasures of our creative spirits, giving voice to the forgotten dreams that linger in the darkest chambers of our hearts. And lo, we discover that even the spiky and the scary can, in their own right, be loving and daring, revealing the multifaceted nature of art and the boundless realms of human emotion.";

    let imageUrl = "images/main/pagecover.jpg"; // Replace with the URL of your image.
</script>

<section class="compact-section">
    <div class="image">
        <img src={imageUrl} alt="Image" />
    </div>
    <div class="bio">
        <p>{bio}</p>
    </div>
</section>

<style>
    .compact-section {
        display: flex;
        align-items: center;
        max-width: 800px;
        margin: 0 auto;
        padding: 20px;
    }

    .image {
        flex: 1;
        margin-right: 90px;
    }

    img {
        max-width: 400px;
        max-height: 100%;
    }

    .bio {
        flex: 2;
    }

    p {
        font-size: 12px;
        line-height: 2.4;
        font-weight: bold;
    }
</style>
