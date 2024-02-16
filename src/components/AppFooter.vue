<script>
import FooterLink from './Footer/FooterLink.vue';
import FormEmail from './Footer/FormEmail.vue';
export default {
    name: 'AppFooter',
    components: { FooterLink, FormEmail },
    props: {
        menus: Array
    }
}
</script>

<template>
    <footer>
        <div class="container">
            <div class="top-footer">
                <div class="footer-row">
                    <div class="footer-col" v-for="(menu, i) in menus" :key="i">
                        <FooterLink :title="menu.title" :links="menu.links" />
                    </div>
                </div>
                <FormEmail class="flex-grow-1" />
            </div>
            <div class="bottom-footer">
                <img src="../assets/img/anime-whitelogo.png" alt="white-logo" class="img-fluid">
                <address class="fs-5"> © Anime Tech, Theme by HasnainDEV</address>
            </div>
        </div>
    </footer>
</template>

<style lang="scss" scoped>
footer {
    background-color: #bf1d2e;
    padding: 3rem;
    color: white;
    border-top: 5px solid #333333;
    margin-top: 20px;
    position: relative;

    .top-footer {
        border-bottom: 1px solid white;
        padding-bottom: 3rem;

        display: flex;
        align-items: center;

        .footer-row {
            display: flex;
            width: 75%;

            .footer-col {
                flex-basis: calc(100% / 4);
                gap: 2rem;
                font-weight: 600;
            }
        }
    }

    .bottom-footer {

        margin-top: 2.5rem;
        display: flex;
        align-items: center;
        justify-content: space-between;

        img {
            max-width: 250px;
        }
    }
}

footer::before {
    content: '';
    position: absolute;
    top: 0;
    right: 50%;
    width: 30px;
    height: 20px;
    background: linear-gradient(#333333 00%, #333333 50%, transparent 50%, transparent);
}
</style>
