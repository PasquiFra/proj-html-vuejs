<script>
import FinalIcons from './MainBody/BottomComps/FinalIcons.vue';
import BottomMain from './BottomMain.vue';
import TopMain from './TopMain.vue';
import LifestylesCarousel from './MainBody/TopComps/LifestylesCarousel.vue';
export default {
    name: 'AppMain',
    components: { BottomMain, TopMain, FinalIcons, LifestylesCarousel }
}
</script>

<template>
    <LifestylesCarousel />
    <div class="container">
        <TopMain />
    </div>
    <div class="banner">
        <div class="container">
            <img src="../assets/img/page-banner-1.webp" alt="banner" class="rounded">
        </div>
    </div>
    <div class="container">
        <BottomMain />
    </div>
    <FinalIcons />
</template>

<style lang="scss" scoped>
.banner {
    padding: 2rem;
    background-color: #F3F3F3;
    margin: 3rem 0;
    text-align: center;

    img {
        width: 100%;
    }
}
</style>
