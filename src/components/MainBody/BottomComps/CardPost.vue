<script>
export default {
    name: 'CardPost',
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
    <div class="card border-0" style="width: 26.5rem;">
        <div class="card-img">
            <div id="labels" class="p-4">
                <a href="#" class="label" v-for="label in labels">{{ label }}</a>
            </div>
            <img :src="`src/assets/img/${src}`" :alt="title" class="card-img-top">
        </div>
        <div class="card-body text-center rounded-bottom">
            <h5 class="card-title fw-bold">{{ title }}</h5>
            <span class="date text-secondary fw-bold">{{ date }}</span>
            <p class="card-text">Lorem ipsum dolor sit amet consectetur adipisicing elit. Facilis nulla sapiente placeat
                illum quidem...</p>
            <button type="button" class="rounded-pill fw-bold"> Read More</button>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.card-body {
    background-color: #F3F3F3;
}

h5:hover {
    color: #BF1D2E;
}

button {
    width: 40%;
    height: 2.5rem;
    background-color: #BF1D2E;
    font-weight: bold;
    color: white;
    cursor: pointer;
    border: none;

    &:hover {
        background-color: #545454;
        transition: background-color .3s ease;
    }
}

a {
    text-decoration: none;
    color: black;
}

.card-img {
    position: relative;

    #labels {
        position: absolute;
        top: -10px;
    }
}
</style>