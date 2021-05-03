<template>
    <div class="works">
        <!--start head-section-page -->
        <div class="head-section-page">

            <v-container>
                <v-row class="d-flex align-center">
                    <v-col cols="12" lg="6" md="6" sm="6" xm="12">
                        <img src="/pagesImages/services.svg">
                    </v-col>
                    <v-col cols="12" lg="6" md="6" sm="6" xm="12">
                        <h2>{{$t('works')}}</h2>
                    </v-col>
                </v-row>
            </v-container>
            
        </div>
        <!--end head-section-page -->
    </div>
</template>

<script>
export default {
    head() {
        return {
            title: this.$t('works')
        }
    }
}
</script>

<style>

</style>