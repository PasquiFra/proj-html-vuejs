<script>
import { gallery } from '../../../data/_gallery';
import CardPost from './CardPost.vue';
export default {
    name: 'PostsCarousel',
    components: { CardPost },
    data: () => ({
        gallery: [],
        postsPerPage: 3,
        currentPage: 1,
        intervalId: null
    }),
    methods: {
        removeFoodLabels() {
            this.gallery = this.gallery.filter(item => {
                return !item.labels.includes('Food');
            });
        },
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
        this.removeFoodLabels();
        this.startAutoChange();
    }
}

</script>

<template>
    <div class="header-cards d-flex justify-content-between mb-3">
        <div class="title">
            <h3 class="text-uppercase fw-bold">Featured posts</h3>
        </div>
        <div class="buttons-cards">
            <button class="prev" @mouseover="stopAutoChange" @mouseout="startAutoChange" @click="() => navigate('prev')"><i
                    class="fa-solid fa-angle-left fa-lg"></i></button>
            <button class="next" @mouseover="stopAutoChange" @mouseout="startAutoChange" @click="() => navigate('next')"><i
                    class="fa-solid fa-angle-right fa-lg"></i></button>
        </div>
    </div>
    <div class="row-cards">
        <div class="col-card" v-for="(g, id) in currentArray" :key="id">
            <CardPost :src="g.src" :title="g.title" :date="g.date" :labels="g.labels" :id="g.id" />
        </div>
    </div>
</template>

<style lang="scss" scoped>
h4 {
    color: #333333;
}

.buttons-cards {
    display: flex;
    gap: 1.2rem;
}

button {
    outline: none;
    border: none;
    height: 2.5rem;
    width: 2.5rem;
    border-radius: 50%;
    background-color: #333333;
    color: white;
    cursor: pointer;

    &:hover {
        background-color: #BF1D2E;
        transition: background-color .3s ease;
    }
}

.row-cards {
    display: flex;
    justify-content: space-between;
    width: 100%;
    gap: 10px;
    overflow-x: hidden;


    .col-card {
        flex-basis: calc(100% / 3);
    }
}
</style>