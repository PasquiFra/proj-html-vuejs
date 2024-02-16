<script>
export default {
    name: "SearchOffcanvas",
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
        <i class="fa-solid fa-magnifying-glass fs-2"></i>
    </a>
    <div :class="{ 'canvas-overlay': openCanvas }">
        <div class="offcanvas" :class="{ 'show': openCanvas }" id="offcanvasTop">
            <div class="canvas-body d-flex">
                <form>
                    <input type="text" placeholder="Search...">
                </form>
                <i class="fa-solid fa-xmark" type="button" @click="toggleCanvas"></i>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
a {
    color: #545454;

    &:hover {
        color: #BF1D2E;
    }
}

.canvas-overlay {
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    z-index: 2;
    background-color: rgba(0, 0, 0, 0.7);
}

#offcanvasTop {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: transparent;

    height: 100vh;
    width: 100vw;


    .canvas-body {
        position: absolute;
        top: 50%;
        left: 20%;
        z-index: 2;


        align-items: center;
        justify-content: center;

        input {
            text-align: center;
            background-color: transparent;
            width: 50vw;

            border: 0;
            border-bottom: 2px solid white;
            margin-right: 50px;

            font-size: 2rem;
            font-weight: 700;
            color: white;
        }

        i.fa-xmark {
            opacity: 1;
            color: white;
            font-size: 2rem;
            transition: transform 0.5s;

            &:hover {
                transition: transform 0.5s;
                transform: scale(1.2);
            }
        }

    }
}
</style>