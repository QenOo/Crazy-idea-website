<template>
    <div>
        <h1>{{ $t('home') }}</h1>
        
    </div>
</template>

<script>
export default {
    name: 'home',
    data: () => ({
        res: []
    }),
    head() {
        return {
            title: this.$t('home')
        }
    },
    mounted() {
        this.fetchSomething();
    },
    methods: {
        async fetchSomething() {
            const res = await this.$axios.$get('http://127.0.0.1:8000/api/module/teams')
            this.res = res.payload.data;
            console.log(this.res)
        }
    }
};
</script>


<style scoped>


</style>