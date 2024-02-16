<script>
import SearchOffcanvas from './SearchOffcanvas.vue';
import NavMenu from './NavMenu.vue';
import LinksMenu from './LinksMenu.vue';

export default {
    name: 'HeaderNav',
    data: () => ({
        links: [
            {
                name: 'home',
                icon: 'fa-solid fa-house-chimney',
                dropDown: null
            },
            {
                name: 'about us',
                icon: 'fa-solid fa-user',
                dropDown: null
            },
            {
                name: 'lifestyle',
                icon: 'fa-solid fa-suitcase',
                dropDown: 'fa-solid fa-angle-down'
            },
            {
                name: 'stories',
                icon: 'fa-solid fa-book-open-reader',
                dropDown: 'fa-solid fa-angle-down'
            },
            {
                name: 'pages',
                icon: 'fa-solid fa-book',
                dropDown: null
            },
            {
                name: 'contact us',
                icon: 'fa-solid fa-envelope',
                dropDown: null
            }
        ]
    }),
    components: {
        SearchOffcanvas, NavMenu, LinksMenu
    }

}
</script>

<template>
    <div class="header-nav">
        <div class="container py-3">
            <div class="row align-items-center">
                <div class="col-2">
                    <NavMenu />
                </div>
                <div class="col-8">
                    <LinksMenu />
                </div>
                <div class="col-2 d-flex justify-content-end position-relative">
                    <SearchOffcanvas />
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.header-nav {
    border-top: 2px solid #F3F3F3;
    background-color: #fff;
}

a {
    color: #545454;

    &:hover {
        color: #BF1D2E;
    }
}
</style>