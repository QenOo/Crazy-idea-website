<template>
    <v-app dark >
        <!-- ?== My Navbar -->
        <app-navbar />
        <!-- ?== My Navbar -->

        <!-- ?==  content -->
        <v-main>
            <nuxt />
            <v-container>
            </v-container>
        </v-main>
        <!-- ?==  content -->

        <!-- ?== my content -->
        <app-footer />
        <!-- ?== my content -->

        <!-- ?== App Setting -->
        <app-setting />
        <!-- ?== App Setting -->
    </v-app>
</template>

<script>
import appSetting from "../components/app-setting.vue";
import Vuetify from 'vuetify'
import colors from 'vuetify/es5/util/colors'
import AppFooter from '../components/app-footer.vue';


export default {
    components: { appSetting, AppFooter },
    data() {
        return {};
    },
    head() {
        return {
            titleTemplate: this.$t("websiteName") + " => %s",
            title: "Crazy Idea",
            htmlAttrs: {
                lang: this.$i18n.locale
            }
        };
    },
    mounted() {

        if ( this.$i18n.locale == "ar") {
            this.$vuetify.rtl = true;
        } else {
            this.$vuetify.rtl = false;
        }


        // toggle dark mode
        const theme = localStorage.getItem("dark_theme");
        this.$vuetify.theme.themes.light.heading = '#00153F'
        if (theme) {
            if (theme == "true") {
                this.$vuetify.theme.dark = true;
            } else {
                this.$vuetify.theme.dark = false;
                this.$meta().refresh()
            }
        }
    },
    vuetify: new Vuetify({
        theme: {
            dark: true,
            themes: {
                dark: {
                    heading: '#fff',
                    headingtow: '#0861D4',
                    accent: colors.grey.darken3,
                    secondary: colors.amber.darken3,
                    info: colors.teal.lighten1,
                    warning: colors.amber.base,
                    error: colors.deepOrange.accent4,
                    success: colors.green.accent3,
                    textinfo: colors.amber.base,
                },
                light: {
                    heading: '#00153F',
                    headingtow: '#0861D4',
                    secondary: colors.grey.darken1,
                    accent: colors.shades.black,
                    error: colors.red.accent3,
                    background: colors.indigo.lighten5,
                    textinfo: colors.teal.lighten1,
                },
            }
        }
    })
};
</script>


<style>
/* * {
    transition: all ease-in-out .2s;
} */

body  {
    font-family: 'Tajawal', sans-serif !important;
}

[lang="ar"] .v-application {
    font-family: 'Tajawal', sans-serif !important;
}


/*start head-section-page */
.head-section-page {
    background-image: url('/header/bkCover.svg');
    background-size: cover;
    background-position: bottom;
    min-height: calc(100vh - 100px);
    margin-bottom: 40px;
}

.head-section-page img {
    width: 95%;
    height: 95%;
    margin-top: 80px;
}

.head-section-page h2 {
    font-size: 50px;
    color: #fff;
    text-align: center;
}

ul {
    list-style-type: none;
}
/*end head-section-page */
</style>