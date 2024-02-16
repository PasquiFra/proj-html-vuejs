<script>
import { store } from './data/store'
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppFooter from './components/AppFooter.vue';
export default {
  name: 'anime',
  components: { AppHeader, AppMain, AppFooter },
  data: () => ({
    footerMenus: [
      {
        title: 'get started',
        links: [
          { url: '#', text: 'Resoucers' },
          { url: '#', text: 'Tutorials' },
          { url: '#', text: 'Examples' },
          { url: '#', text: 'Docs' },
        ]
      },
      {
        title: 'about',
        links: [
          { url: '#', text: 'Stories' },
          { url: '#', text: 'Community' },
          { url: '#', text: 'Blog' },
          { url: '#', text: 'Brand Assets' },
        ]
      },
      {
        title: 'features',
        links: [
          { url: '#', text: 'Overview' },
          { url: '#', text: 'Design' },
          { url: '#', text: 'Code' },
          { url: '#', text: 'Collaborate' },
        ]
      },
      {
        title: 'quick links',
        links: [
          { url: '#', text: 'Stories' },
          { url: '#', text: 'Community' },
          { url: '#', text: 'Blog' },
          { url: '#', text: 'Brand Assets' },
        ]
      },
    ]
  })
}
</script>



<template>
  <AppHeader />
  <AppMain />
  <AppFooter :menus="footerMenus" />
</template>



<style lang="scss">
@use './assets/scss/style.scss';
</style>
