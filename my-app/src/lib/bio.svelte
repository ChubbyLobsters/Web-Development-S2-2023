<script>
    let bio = "A key street style takeaway from January’s Paris menswear shows: trail running sneakers (mostly those from Salomon) are not A key street style takeaway from January’s Paris menswear shows: trail running sneakers (mostly those from Salomon) are not";
    let bio2 = "A key street style takeaway from January’s Paris menswear shows: trail running sneakers (mostly those from Salomon) are not A key street style takeaway from January’s Paris menswear shows: trail running sneakers (mostly those from Salomon) are not";
    let bio3 = "A key street style takeaway from January’s Paris menswear shows: trail running sneakers (mostly those from Salomon) are not A key street style takeaway from January’s Paris menswear shows: trail running sneakers (mostly those from Salomon) are not";
    let bio4 = "A key street style takeaway from January’s Paris menswear shows: trail running sneakers (mostly those from Salomon) are not A key street style takeaway from January’s Paris menswear shows: trail running sneakers (mostly those from Salomon) are not";
    let bio5 = "A key street style takeaway from January’s Paris menswear shows: trail running sneakers (mostly those from Salomon) are not A key street style takeaway from January’s Paris menswear shows: trail running sneakers (mostly those from Salomon) are not";
    let bio6 = "A key street style takeaway from January’s Paris menswear shows: trail running sneakers (mostly those from Salomon) are not A key street style takeaway from January’s Paris menswear shows: trail running sneakers (mostly those from Salomon) are not";
   
   let imageUrl = "outfitOne.jpg"; // Replace with the URL of your image.
</script>

<main>
    <div class="info-box">
        <div class="image">
            <img src={imageUrl} alt="Image" />
        </div>
        <div class="bio">
            <p>{bio}</p>
            <p>{bio2}</p>
            <p>{bio3}</p>
            <p>{bio4}</p>
            <p>{bio5}</p>
            <p>{bio6}</p>
            <p>{bio}</p>
            <p>{bio2}</p>
            <p>{bio3}</p>
            <p>{bio4}</p>
            <p>{bio5}</p>
            <p>{bio6}</p>
            <p>{bio}</p>
        </div>
    </div>
</main>

<style>
    main {
        text-align: center;
    }

    .info-box {
        display: flex;
        border: 1px solid #ccc;
        border-radius: 8px;
        padding: 20px;
        width: 1500px;
        height:px;
        margin: 0 auto;
        background-color: #f5f5f5;
    }

    .image {
        flex: 1;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .bio {
        flex: 1;
        padding: 10px;
    }

    img {
        max-width: 100%;
        max-height: 100%;
    }
</style>
