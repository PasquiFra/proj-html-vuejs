<script>

export default {
    name: 'CarouselCard',
    props: {
        id: Number,
        src: String,
        title: String,
        date: String,
        labels: Array
    }
}

</script>

<template>
    <div class="card border-0">
        <div class="card-img">
            <div id="labels" class="p-4">
                <a href="#" class="label" v-for="label in labels">{{ label }}</a>
            </div>
            <img :src="`src/assets/img/${src}`" :alt="title" class="card-img-top">
        </div>
        <div class="card-body text-center rounded-bottom">
            <h5 class="card-title fw-bold">{{ title }}</h5>
            <span class="date text-secondary fw-bold">{{ date }}</span>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.card {
    width: 100%;
}

.card-body {
    background-color: #fff;
    width: 100%;
}

h5:hover {
    color: #BF1D2E;
}

.card-img-top {
    width: 100%;

}

.card-img {
    position: relative;

    #labels {
        position: absolute;
        top: -10px;
    }
}

a {
    text-decoration: none;
    color: black;
}
</style>