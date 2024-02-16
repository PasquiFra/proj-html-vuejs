<script>
export default {
    name: "NavMenu",
    data: () => ({
        openCanvas: false,
    }),
    computed: {
        toggleCanvas() {
            this.openCanvas = !this.openCanvas
        }
    }
}
</script>

<template>
    <a href="#" type="button" @click="toggleCanvas">
        <i class="fa-solid fa-bars fs-2"></i>
    </a>

    <div class="offcanvas offcanvas-start" :class="{ 'show': openCanvas }" id="offcanvasMenu">
        <div class="offcanvas-header">
            <div>
                <i class="fa-solid fa-xmark" type="button" @click="toggleCanvas"></i>
            </div>
        </div>
        <div class="offcanvas-body">
            <img class="offcanvas-logo" src="../../assets/img/anime-logo.webp" alt="">
            <p class="px-3 fw-medium fs-6">Lorem ipsum dolor sit amet consectetur adipisicing elit. Quo dolores maiores
                ullam
                aliquam
                consectetur rerum.
            </p>
            <picture class="offcanvas-pics d-flex">
                <img src="../../assets/img/music-love.webp" alt="">
                <img src="../../assets/img/best-places.webp" alt="">
                <img src="../../assets/img/anime-fashion.webp" alt="">
            </picture>
            <div class="contacts">
                <ul class="list-unstyled d-flex align-items-center py-2 ps-4 mb-0">
                    <li><a href="#" class="text-decoration-none"><i class="fa-solid fa-clock me-2"></i>Sun - Sat : 9:00 AM -
                            18:00 PM</a></li>
                    <li><a href="#" class="text-decoration-none"><i
                                class="fa-solid fa-envelope me-2"></i>contact@domain.com</a></li>
                    <li><a href="#" class="text-decoration-none"><i class="fa-solid fa-phone-volume me-2"></i>(+82) 8123 456
                            789</a></li>
                </ul>
            </div>
            <div class="socials">
                <ul class="list-unstyled d-flex align-items-center py-2 ps-4 mb-0">
                    <li><a href="#"><i class="fa-brands fa-facebook-f"></i></a></li>
                    <li><a href="#"><i class="fa-brands fa-twitter"></i></a></li>
                    <li><a href="#"><i class="fa-brands fa-instagram"></i></a></li>
                    <li><a href="#"><i class="fa-brands fa-youtube"></i></a></li>
                </ul>
            </div>
        </div>
        <div :class="{ 'canvas-overlay': openCanvas }"></div>
    </div>
</template>

<style lang="scss" scoped>
.canvas-overlay {
    position: fixed;
    top: 0;
    bottom: 0;
    left: 30vw;
    right: 0;
    z-index: 1;
    background-color: rgba(0, 0, 0, 0.7);
}

a {
    color: #545454;

    &:hover {
        color: #BF1D2E;
    }
}

#offcanvasMenu {
    width: 30vw;

    .offcanvas-header {
        position: relative;

        div {
            position: absolute;
            top: 0px;
            left: 100%;

            width: 65px;
            height: 50px;
            background-color: #BF1D2E;
            z-index: 2;
            cursor: pointer;

            i.fa-xmark {
                font-size: 16px;
                position: absolute;
                top: 50%;
                left: 50%;
                translate: -50% -50%;
                color: white;
                padding: 2px 4px 2px 5px;
                border: 3px solid white;
                border-radius: 4px;
                background-color: #BF1D2E
            }
        }
    }

    .offcanvas-body {
        padding: 140px 40px;
        text-align: center;

        .offcanvas-logo {
            width: 300px;
            height: auto;
            margin: 30px 0;
        }


        picture {
            width: 100%;
            height: 110px;
            justify-content: center;
            margin-bottom: 20px;
            margin-top: 30px;

            img {
                border-radius: 10px;
                padding: 5px;
                object-fit: cover;

            }
        }
    }
}

.socials {
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    right: 15px;

    ul {
        list-style: none;
        display: flex;
        flex-direction: row;
        align-items: center;
        gap: 10px;

        li {

            i {
                background-color: #bf1d2e;
                width: 35px;
                height: 35px;
                font-size: 15px;
                border-radius: 50%;
                color: #ffffff;
                text-align: center;
                line-height: 35px;
                transition: color 0.3s, background-color 0.4s;

                &:hover {
                    color: #fff;
                    background-color: #545454;
                }
            }
        }
    }
}

.contacts {
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    right: 15px;
    margin-bottom: 20px;

    ul {
        list-style: none;
        display: flex;
        flex-direction: column;
        align-items: center;

        li {
            cursor: pointer;
            line-height: 30px;
            font-weight: 500;

            i {

                font-size: 16px;
                color: #bf1d2e;
                text-align: center;
                transition: color 0.3s, background-color 0.4s;

            }

            &:hover {
                i {
                    color: #545454;
                }

                a {
                    color: #BF1D2E;
                }
            }
        }
    }
}
</style>