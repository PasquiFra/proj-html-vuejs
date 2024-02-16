<script>
import { gallery } from '../../../data/index'
export default {
    name: 'Lifestyle & Stories',
    data: () => ({
        gallery,
        shuffledArray: []
    }),
    methods: {
        getRandomElements(array, n) {
            this.shuffledArray = [...array];
            this.shuffledArray.sort(() => Math.random() - 0.5);
            console.log(this.shuffledArray)
            return this.shuffledArray.splice(0, n)
        },

        scrImage() {
            const src = `../../../assets/img/${pic.src}`
        }
    }
}
</script>

<template>
    <section class="my-5">
        <div class="section-header d-flex justify-content-between">
            <h3 class="section-title">Lifestyle & Stories</h3>
            <div class="btn-group">
                <button @click="getRandomElements(gallery, 9)">All</button>
                <button>Lifestyle</button>
                <button>Stories</button>
            </div>
        </div>

        <div class="section-image d-flex">
            <div class="left-poster">
                <img class="poster" src="../../../assets/img/best-places.webp" alt="Lifestyle">
                <div class="label">Lifestyle</div>
                <div class="info">
                    <div>
                        <span><i class="fa-solid fa-user"></i> demo </span>
                        <span><i class="fa-solid fa-calendar-days"></i> December 25, 2022</span>
                    </div>
                    <h5>Place For A Road Trip</h5>
                </div>
            </div>


            <div class="right-gallery">
                <!--Pezzo dinamico da finire-->
                <!-- <div class="lifestyle-card" v-for="pic in gallery" :key="pic.id">
                    <div class="card-gallery d-flex align-items-center gap-3">
                        <div class="gallery-poster">
                            <img :src="`../../../assets/img/${pic.src}`" :alt="pic.labels[0]">
                            <div class="label">{{ pic.labels[0] }}</div>
                        </div>
                        <div class="gallery-info">
                            <div>
                                <span><i class="fa-solid fa-user"></i> demo </span>
                                <span><i class="fa-solid fa-calendar-days"></i> {{ pic.date }}</span>
                            </div>
                            <h5>{{ pic.title }}</h5>
                        </div>
                    </div>
                    <hr>
                </div> -->


                <div class="card-gallery d-flex align-items-center gap-3">
                    <div class="gallery-poster">
                        <img src="../../../assets/img/music-love.webp" alt="Culture">
                        <div class="label">Culture</div>
                    </div>
                    <div class="gallery-info">
                        <div>
                            <span><i class="fa-solid fa-user"></i> demo </span>
                            <span><i class="fa-solid fa-calendar-days"></i> December 25, 2022</span>
                        </div>
                        <h5>Music The Love Of My Life</h5>
                    </div>
                </div>
                <hr>
                <div class="card-gallery d-flex align-items-center gap-3">
                    <div class="gallery-poster">
                        <img src="../../../assets/img/success-story.webp" alt="Culture">
                        <div class="label">Culture</div>
                    </div>
                    <div class="gallery-info">
                        <div>
                            <span><i class="fa-solid fa-user"></i> demo </span>
                            <span><i class="fa-solid fa-calendar-days"></i> December 25, 2022</span>
                        </div>
                        <h5>The Best Success Stories</h5>
                    </div>
                </div>
                <hr>
                <div class="card-gallery d-flex align-items-center gap-3">
                    <div class="gallery-poster">
                        <img src="../../../assets/img/anime-fashion.webp" alt="Fashion">
                        <div class="label">Fashion</div>
                    </div>
                    <div class="gallery-info">
                        <div>
                            <span><i class="fa-solid fa-user"></i> demo </span>
                            <span><i class="fa-solid fa-calendar-days"></i> December 25, 2022</span>
                        </div>
                        <h5>Fashion Tren Now A Days</h5>
                    </div>
                </div>
            </div>
        </div>

    </section>
</template>

<style lang="scss" scoped>
@use '../../../assets/scss/vars' as *;

.section-title {
    text-transform: uppercase;
    color: $dark-gray;
}

button {
    text-transform: uppercase;
    color: $white;
    background-color: #545454;
    margin-left: 20px;
    border-radius: 5px;
    border: 1px solid currentColor;
    padding: 5px 20px;
}

button:hover {
    background-color: $red;
}

.section-image {
    margin-top: 20px;
    width: 100%;
    height: 500px;

}

//_________________________________________

//Left Poster
.left-poster {
    width: 60%;
    height: 100%;

    position: relative;
}

.left-poster::before {
    position: absolute;
    top: 0;
    right: 0;
    left: 0;
    bottom: 0;
    background-color: rgba(0, 0, 0, 0.5);
    border-radius: 5px;
    content: '';
}

.left-poster:hover {
    opacity: .8;
}

.poster {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 5px;
}

.label {
    color: $dark-gray;
    font-size: 14px;
    font-weight: 500;

    position: absolute;
    top: 15px;
    left: 15px;
}

.info {
    color: $white;
    font-weight: 600;

    position: absolute;
    bottom: 50px;
    left: 20px;
}

//Right Galler
.right-gallery {
    padding: 0 20px;

    width: 40%;
    height: 100%;

    overflow: auto;
}

.right-gallery img {
    width: 200px;
    border-radius: 5px;
}

.gallery-info {
    color: $dark-gray;
    font-weight: 600;
}

.gallery-poster {
    position: relative;
}

.gallery-poster:hover {
    opacity: 0.8;
}


.gallery-poster::before {
    position: absolute;
    top: 0;
    right: 0;
    left: 0;
    bottom: 0;
    background-color: rgba(0, 0, 0, 0.5);
    border-radius: 5px;
    content: '';
}
</style>