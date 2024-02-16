<script>

import { gallery } from '../../../data/_gallery';
import CarouselCard from '../TopComps/CarouselCard.vue';

export default {
    name: 'LifestylesCarousel',
    data: () => ({
        gallery: [],
        postsPerPage: 4,
        currentPage: 1,
        intervalId: null
    }),
    components: { CarouselCard },
    methods: {
        updateCurrentPage(page) {
            this.currentPage = page;
        },
        navigate(direction) {
            if (direction === 'next') {
                this.currentPage = (this.currentPage % this.totalPages) + 1;
            } else if (direction === 'prev') {
                this.currentPage = (this.currentPage - 2 + this.totalPages) % this.totalPages + 1;
            }
        },
        startAutoChange() {
            this.intervalId = setInterval(() => {
                this.navigate('next');
            }, 2500);
        },
        stopAutoChange() {
            clearInterval(this.intervalId);
        }
    },
    computed: {
        totalPages() {
            return Math.ceil(this.gallery.length / this.postsPerPage);
        },
        currentArray() {
            const start = (this.currentPage - 1) * this.postsPerPage;
            const end = start + this.postsPerPage;
            return this.gallery.slice(start, end);
        }
    },
    created() {
        this.gallery = gallery;
        this.startAutoChange();
    }
}


</script>

<template>
    <div class="background">
        <button class="next" @mouseover="stopAutoChange" @mouseout="startAutoChange" @click="() => navigate('prev')"><i
                class="fa-solid fa-angle-right fa-lg"></i></button>
        <button class="prev" @mouseover="stopAutoChange" @mouseout="startAutoChange" @click="() => navigate('next')"><i
                class="fa-solid fa-angle-left fa-lg"></i></button>
        <div class="row-cards">
            <div class="col-card" v-for="(g, id) in currentArray" :key="id">
                <CarouselCard :src="g.src" :title="g.title" :date="g.date" :labels="g.labels" :id="g.id" />
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
h4 {
    color: #333333;
}

.background {
    padding: 2rem 2rem 1rem 2rem;
    background-color: #F3F3F3;
    margin-bottom: 3rem;
    position: relative;
}

.prev {
    position: absolute;
    bottom: 50%;
    left: 50px;
    z-index: 1;
}

.next {
    position: absolute;
    right: 50px;
    bottom: 50%;
    z-index: 1;
}

button {
    outline: none;
    border: none;
    height: 2.5rem;
    width: 2.5rem;
    border-radius: 50%;
    background-color: #fff;
    color: #BF1D2E;
    cursor: pointer;

    &:hover {
        background-color: #BF1D2E;
        color: white;
        transition: background-color .3s ease;
    }
}


.row-cards {
    width: 100%;
    min-height: 100px;
    margin-bottom: 20px;
    display: flex;


    gap: 14px;
    flex-shrink: 0;
    overflow-x: scroll;
    overflow-y: hidden;


    .col-card {
        width: calc(100% / 4 - 10px);
        flex-shrink: 0;
        height: 380px;
    }
}

.row-cards::-webkit-scrollbar {
    display: none;
}
</style>