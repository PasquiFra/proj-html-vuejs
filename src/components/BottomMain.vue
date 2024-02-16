<script>
import VideoPlayer from './MainBody/BottomComps/VideoPlayer.vue';
import PostsCarousel from './MainBody/BottomComps/PostsCarousel.vue';
export default {
    name: 'BottomMain',
    components: { VideoPlayer, PostsCarousel }
}
</script>

<template>
    <PostsCarousel />
    <VideoPlayer />
</template>

<style lang="scss"></style>
