<script>
import MainNews from './MainBody/TopComps/MainNews.vue';
import LifestyleStories from './MainBody/TopComps/LifestyleStories.vue';

import { gallery } from '../data/index'

export default {
    name: 'TopMain',
    components: { MainNews, LifestyleStories }
}
</script>


<template>
    <MainNews />
    <LifestyleStories />
</template>

<style lang="scss" scoped></style>
