<script>

export default {
    name: "DisplayCard",
    props: {
        object: Object
    }
}

</script>

<template>
    <div class="card">
        <picture>
            <div class="img filter"></div>
            <img class="img" :src="`src/assets/img/${object.src}`" :alt="object.title">
        </picture>
        <div id="labels" class="p-4">
            <a href="#" class="label" v-for="label in object.labels">{{ label }}</a>
        </div>
        <div class="info p-4">
            <span class="w-100">
                <i class="fa-solid fa-user p-1"></i> demo
                <i class="fa-solid fa-calendar-days p-1"></i>
                <span>{{ object.date }}</span>
            </span>
            <h6 class="w-100">{{ object.title }}</h6>
        </div>
    </div>
</template>

<style lang="scss" scoped>
a {
    text-decoration: none;
    color: black;

    &:hover {
        color: #bf1d2e;
    }
}

.card {
    flex-shrink: 0;
    flex-grow: 1;
    flex-direction: column;
    justify-content: space-between;
    text-align: center;

    border: 0;
    background-color: transparent;

    width: 100%;
}

picture {
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    z-index: -1;


    .img {
        position: absolute;
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
        z-index: -1;

        width: 100%;
        height: 100%;
        border-radius: 5px;

        &.filter {
            z-index: 1;
            background-color: rgba(0, 0, 0, 0.5);

        }
    }
}

.card:hover::after {
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    z-index: -1;

    background-color: rgba(255, 255, 255, 0.2);
    content: "";
}

.info {
    display: flex;
    flex-wrap: wrap;

    color: white;
    font-weight: 600;
    font-size: 1rem;

    h6 {
        font-weight: 700;
        font-size: 1.1rem;
    }
}
</style>