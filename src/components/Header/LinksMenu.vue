<script>
import { links } from '../../data/index';
export default {
    name: "LinksMenu",
    data: () => ({
        links
    }),
}
</script>

<template>
    <ul class="list-unstyled d-flex flex-row justify-content-center mb-0">
        <li v-for="(link, i) in links" :key="link.name" class="text-uppercase mx-2 fs-6">
            <a href="#" class="text-decoration-none fw-semibold"><i :class="link.icon" class="px-2"></i>{{
                link.name
            }}<i class="ms-2" :class="link.dropDown"></i></a>
        </li>
    </ul>
</template>

<style lang="scss" scoped>
ul {
    a {
        color: #000;

        &:hover {
            color: #BF1D2E;
        }
    }
}
</style>
