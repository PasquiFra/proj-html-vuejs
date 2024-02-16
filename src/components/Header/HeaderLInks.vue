<script>
import CarouselHeaderTop from './CarouselHeaderTop.vue'
import { gallery } from '../../data/_gallery'

export default {
    name: 'HeaderLinks',
    data: () => ({
        gallery,
        currentId: 1,
        intervalId: null

    }),
    components: {
        CarouselHeaderTop
    },
    computed: {
        setCurrentId() {
            let activeId
            if (this.currentId < 1) {
                this.currentId = (this.gallery.length)
                return activeId = this.currentId
            } else if (this.currentId > this.gallery.length) {
                this.currentId = 1
                return activeId = this.currentId
            } else {
                return activeId = this.currentId
            }
        }
    },
    methods: {
        navigate(direction) {
            if (direction === 'next') {
                this.currentId++;
            } else if (direction === 'prev') {
                this.currentId--;
            }
        },
        startAutoChange() {
            this.intervalId = setInterval(() => {
                this.navigate('next');
            }, 2500);
        },
    },
    created() {
        this.gallery = gallery;
        this.startAutoChange();
    }
}
</script>

<template>
    <div class="header-links">
        <div class="container d-flex justify-content-between">
            <div class="news-updates d-flex">
                <h2 class="text-uppercase fs-6 py-1 px-3 mb-0 text-white align-items-center d-flex">
                    news updates
                </h2>
                <CarouselHeaderTop :activeId="setCurrentId" />
            </div>
            <div class="links d-flex">
                <ul class="list-unstyled d-flex align-items-center py-1 px-3 mb-0">
                    <li type="button" @click="() => navigate('prev')"><i class="fa-solid fa-chevron-left mx-4"></i></li>
                    <li type="button" @click="() => navigate('next')"><i class="fa-solid fa-chevron-right"></i></li>
                </ul>

                <div class="socials">
                    <ul class="list-unstyled d-flex align-items-center py-2 ps-4 mb-0">
                        <li><a href="#"><i class="fa-brands fa-facebook-f"></i></a></li>
                        <li><a href="#"><i class="fa-brands fa-twitter"></i></a></li>
                        <li><a href="#"><i class="fa-brands fa-instagram"></i></a></li>
                        <li><a href="#"><i class="fa-brands fa-youtube"></i></a></li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.header-links {
    background-color: #BF1D2E;
}

h2 {
    background-color: #545454;
}

.links {
    ul {
        color: white;

        li {
            &:hover {
                color: #3D3233;
                cursor: pointer;
            }
        }
    }
}

.socials {
    ul {
        list-style: none;
        display: flex;
        flex-direction: row;
        align-items: center;
        gap: 10px;

        li {

            i {
                background-color: #fff;
                width: 30px;
                height: 30px;
                font-size: 16px;
                border-radius: 50%;
                color: #BF1D2E;
                text-align: center;
                line-height: 30px;
                transition: color 0.3s, background-color 0.4s;

                &:hover {
                    color: #fff;
                    background-color: #545454;
                }
            }
        }
    }
}
</style>