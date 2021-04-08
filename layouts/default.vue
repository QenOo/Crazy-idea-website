<template>
    <v-app dark>
        <!-- ?== My Navbar -->
        <app-navbar />
        <!-- ?== My Navbar -->

        <!-- ?==  content -->
        <v-main>
            <v-container>
                <nuxt />
            </v-container>
        </v-main>
        <!-- ?==  content -->

        <!-- ?== my content -->
        <v-footer app>
            <span>&copy; {{ new Date().getFullYear() }}</span>
        </v-footer>
        <!-- ?== my content -->

        <!-- ?== App Setting -->
        <app-setting />
        <!-- ?== App Setting -->
    </v-app>
</template>

<script>
import appSetting from "../components/app-setting.vue";
export default {
    components: { appSetting },
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
        if (theme) {
            if (theme == "true") {
                this.$vuetify.theme.dark = true;
            } else {
                this.$vuetify.theme.dark = false;
            }
        }
    }
};
</script>


<style>
</style>