<template>
    <div class="teams mt-12">

        <v-sheet class="mx-auto" max-width="1200" >
            <v-slide-group v-model="model" class="pa-4" center-active show-arrows >
                <v-slide-item v-for="item in this.res" :key="item.id" v-slot="{ active, toggle }" >
                    <v-card elevation="0" :color="active ? 'gray' : ''" class="ma-4" height="400" width="300" @click="toggle" >
                        <v-row
                            class="fill-height"
                            align="center"
                            justify="center"
                        >

                        
                            <div v-if="!active" class="user">
                                <img :src="$images(item.image)" />
                                <div class="user-info">
                                    <h4 class="heading--text">{{item.name}}</h4>
                                    <p class="secondary--text">{{item.job_title}}</p>
                                </div>
                            </div>
                            
                            <v-scale-transition>
                                <img v-if="active" width="100%" height="100%" :src="$images(item.description, 'medium')" />
                            </v-scale-transition>
                        </v-row>
                    </v-card>
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
                let url = process.env.moduleUrl + 'team';
                let image = process.env.imageUrl;
                console.log(image)
                const res = await this.$axios.$get(url);
                this.res = res.payload.data;
            }
        }
    }
</script>

<style>
.user {
    text-align: center;
    width: 100%;
    height: 100%;
}
.user img {
    width: 100%;
}

.user-info {
    margin-top: 20px;
}

.user-info h4 {
    font-size: 20px;
}
</style>