<script>
import HeaderLinks from './Header/HeaderLInks.vue'
import HeaderAds from './Header/HeaderAds.vue'
import HeaderNav from './Header/HeaderNav.vue'
export default {
    name: 'AppHeader',
    components: { HeaderLinks, HeaderAds, HeaderNav }
}
</script>

<template>
    <header>
        <HeaderLinks />
        <HeaderAds />
        <HeaderNav />
    </header>
</template>

<style lang="scss" scoped>
header {
    background-color: blue;
    width: 100%;
}
</style>
