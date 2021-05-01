<template>
    <div class="clients py-16">

        <h5 class="text-sec-head text-center">{{$t('clientsweworkfor')}}</h5>
        
        <v-sheet
            class="mx-auto pa-10"
            max-width="1200"
        >
            <v-slide-group show-arrows v-model="model" >
                <v-slide-item
                    v-for="item in this.res"
                    :key="item.id"
                >
                    <img class="imageClient" :src="$images(item.client_image, 'medium')" />
                </v-slide-item>
            </v-slide-group>
        </v-sheet>

    </div>
</template>

<script>
export default {
    data: () => ({
        model: null,
        res: [],
    }),
    mounted() {
            this.fetchSomething();
    },
    methods: {
        async fetchSomething() {
            let url = process.env.moduleUrl + 'client';
            let image = process.env.imageUrl;
            console.log(image)
            const res = await this.$axios.$get(url);
            this.res = res.payload.data;
        }
    }
}
</script>

<style>
.imageClient {
    width: 150px;
    height: 60px;
    margin: 0 100px;
}

.text-sec-head {
    font-size: 33px;
    margin: 50px 0 60px 0;
}

</style>