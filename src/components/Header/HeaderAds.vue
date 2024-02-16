<script>
export default {
    name: 'HeaderAds'
}
</script>

<template>
    <div class="header-ads">
        <div class="container d-flex align-items-center justify-content-between py-3">
            <div>
                <img id="logo" src="../../assets/img/anime-logo-300x89.webp">
            </div>
            <div class="banner">
                <img class="rounded" src="../../assets/img/header-banner.webp">
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
#logo {
    width: auto;
    height: 4rem;
}

.header-ads {
    background-color: #FFFFFF;
}
</style>