<template>
    <div class="works">
                <!--start head-section-page -->
                <div class="head-section-page">
                    <v-container>
                        <v-row class="d-flex align-center">
                            <v-col lg="6" md="6" sm="12">
                                <img src="/pagesImages/Works.svg">
                            </v-col>
                            <v-col lg="6" md="6" sm="12">
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