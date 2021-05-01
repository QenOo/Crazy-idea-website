<template>
    <div class="teams py-16">

        <div class="heading-section text-center">
            <div class="textinfo--text"> <span>|</span> {{$t('ourSpecialist')}} </div>
            <h4> {{$t('ourSeccessfulTeam')}} </h4>
            <p class="des">
                {{$t('desTeam')}}
            </p>
        </div>

        <v-sheet class="mx-auto" max-width="1200" >
            <v-slide-group v-model="model" class="pa-4" center-active show-arrows >
                <v-slide-item v-for="item in this.res" :key="item.id" v-slot="{ active, toggle }" >
                    <v-card elevation="0" :color="active ? 'gray' : ''" class="ma-4" height="400" width="300" @click="toggle" >
                        <v-row
                            class="fill-height"
                            align="center"
                            justify="center"
                        >

                            <img v-if="!active" width="100%" height="100%" :src="$images(item.description, 'medium')" />
                            
                            <v-scale-transition>
                                <div v-if="active" class="user">
                                    <img :src="$images(item.image, 'small')" />
                                    <div class="user-info">
                                        <h4 class="heading--text">{{item.name}}</h4>
                                        <p class="secondary--text">{{item.job_title}}</p>
                                    </div>
                                </div>
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

<style scoped>
.user {
    text-align: center;
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-wrap: wrap;
}
.user img {
    width: 100%;
    height: 80%;
}

.user-info h4 {
    font-size: 20px;
}

.heading-section h4 {
    margin-top: 2px;
    line-height: 1.8;
    font-size: 30px;
    margin-bottom: 15px;
    font-weight: bolder;
}
.heading-section .des {
    color: #c3c3c3;
    margin-bottom: 50px;
    font-weight: 600;
    width: 45%;
    display: block;
    margin: 0 auto 50px auto;
}


</style>