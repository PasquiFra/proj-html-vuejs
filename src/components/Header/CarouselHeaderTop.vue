<script>

import { gallery } from '../../data/_gallery'

export default {
    name: 'CarouselHeaderTop',
    data: () => ({
        gallery,
        activeCard: "",
    }),
    computed: {
        SetActiveId() {
            return this.activeCard = this.activeId
        }
    },
    props: {
        activeId: Number
    },
    methods: {
        isActive(id) {
            if (this.SetActiveId === id) return "d-block"
            else return
        },

    },
}
</script>

<template>
    <div v-for="{ id, title, src } in this.gallery" :key="id" class="slide" :class="isActive(id)">
        <div class="d-flex">
            <picture class="carousel-img">
                <img src="../../assets/img/anime-fashion.webp" class="img-fluid" :alt="img">
            </picture>
            <h3 class="text-uppercase fs-6 py-1 px-3 mb-0 align-items-center d-flex fw-bolder"> 05:35 {{ title }}
            </h3>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.carousel-img {
    height: 50px;
    width: auto;

    img {
        height: 100%;
        width: auto;
    }
}

.slide {
    display: none;
}

h3 {
    color: #fff;

    &:hover {
        color: #3D3233;
        cursor: pointer;
    }
}
</style>
