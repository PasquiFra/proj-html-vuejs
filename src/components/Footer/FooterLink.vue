<script>
export default {
    name: 'FooterLink',
    props: {
        title: String,
        links: Array
    }
}
</script>

<template>
    <h5>{{ title }}</h5>
    <ul class="p-0">
        <li v-for="link in links"><a :href="link.url">{{ link.text }}</a></li>
    </ul>
</template>

<style lang="scss" scoped>
ul li {
    list-style-type: none;
    line-height: 1.8;

    a {
        text-decoration: none;
        color: white;
        cursor: pointer;

        &:hover {
            color: grey;
        }
    }
}

h5 {
    text-transform: uppercase;
}
</style>