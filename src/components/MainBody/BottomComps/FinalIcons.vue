<script>
export default {
    name: 'FinalIcons'
}
</script>

<template>
    <div class="container-fluid">
        <div class="gallery-row">
            <div class="gallery-col" id="fashion">
                <img src="../../../assets/img/anime-fashion.webp" alt="">
                <div class="white-rectangle">

                </div>
                <div class="text-container">
                    <h4>Fashion</h4>
                    <p class="post">3 posts</p>

                </div>
            </div>

            <div class="gallery-col" id="culture">
                <img src="../../../assets/img/success-story.webp" alt="">
                <div class="white-rectangle">

                </div>
                <div class="text-container">
                    <h4>Culture</h4>
                    <p class="post">3 posts</p>

                </div>
            </div>

            <div class="gallery-col" id="food">
                <img src="../../../assets/img/healthy-foods.webp" alt="">
                <div class="white-rectangle">

                </div>
                <div class="text-container">
                    <h4>Food</h4>
                    <p class="post">3 posts</p>

                </div>
            </div>

            <div class="gallery-col" id="lifestyle">
                <img src="../../../assets/img/visit-france.webp" alt="">
                <div class="white-rectangle">
                </div>
                <div class="text-container">
                    <h4>Lifestyle</h4>
                    <p class="post">3 posts</p>

                </div>
            </div>

            <div class="gallery-col" id="stories">
                <img src="../../../assets/img/travel-alone.webp" alt="">
                <div class="white-rectangle">

                </div>
                <div class="text-container">
                    <h4>Stories</h4>
                    <p class="post">3 posts</p>

                </div>
            </div>

            <div class="gallery-col text-center" id="travel">
                <img src="../../../assets/img/best-places.webp" alt="">
                <div class="white-rectangle">
                </div>
                <div class="text-container">
                    <h4>Travel</h4>
                    <p class="post">3 posts</p>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss">
.gallery-row {
    display: flex;
    justify-content: space-between;
    gap: 10px;
    padding: 0 -1rem;
}

.white-rectangle {
    width: 75%;
    height: 75%;
    border: 1px solid transparent;
    text-transform: uppercase;
    font-weight: 700;
    z-index: 1;
    position: absolute;
    top: 50%;
    left: calc(50% - 25px);
    transform: translate(-50%, -50%);
    transition: all .4s ease;
}

.gallery-col {
    border-radius: 5px;
    width: calc(100% / 6 - 20px);
    height: 200px;
    cursor: pointer;
    background-position: center;
    background-size: cover;
    background-color: rgba(0, 0, 0, 0.655);
    overflow: hidden;
    transition: all 0.4 ease;


    /*Position relative per opacità statica */
    position: relative;



    figure {
        background-color: #bf1d2e;
        border-radius: 5px;
        transition: all .3s ease-in-out;

    }

    img {
        position: absolute;
        right: 0;
        border-radius: 5px;
        width: 350px;
        object-fit: contain;
        overflow: hidden;
        opacity: 1;
        transition: background-color .3s ease-in-out;
        transition: transform .5s ease;
        opacity: 0.5;
        background-color: rgb(0, 0, 0);
        /* Green background with 30% opacity */


    }
}


/* Opacity nera statica */
.gallery-col::before {
    position: absolute;
    top: 0;
    right: 0;
    left: 0;
    bottom: 0;
    background-color: rgba(0, 0, 0, 0.5);
    border-radius: 5px;
    content: '';
}

/* Opacity rossa all'hover */
.gallery-col:hover {
    background-color: rgb(255, 0, 0);
    transform: translateX(-1px);


}


.gallery-col:hover img {
    transform: translateX(40px);
    opacity: 0.4;


}

.gallery-col:hover .white-rectangle {
    transform: translate(calc(-50% + 25px), -50%);
    border: 1px solid white;
}




.text-container {
    width: 50%;
    height: 50%;
    position: absolute;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-evenly;
    top: 25%;
    left: 25%;

    .post {
        visibility: hidden;
        transition: all .4s ease;
        transform: translateX(-25px);
        color: transparent;
        text-transform: uppercase;
        font-size: 0.8rem;

    }

    h4 {
        color: white;
        text-transform: uppercase;
        margin: 0 auto;
        font-weight: 600;
    }
}


.gallery-col:hover .post {
    visibility: visible;
    transform: translateX(1px);
    color: white;
}
</style>
