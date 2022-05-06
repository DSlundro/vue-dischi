<template>
    <main>
        <div class="container py-5" v-if="!loading">
            <div class="row row-cols-2 row-cols-sm-2 row-cols-md-2 row-cols-lg-3 row-cols-xl-4 row-cols-xxl-5">
                <SiteAuthor :element="element" v-for="(element, index) in filterGenre" :key="index" /> 
            </div>
        </div>
        <div v-else class="d-flex min-vh-100 justify-content-center align-items-center">
            <h1>Loading...</h1>
        </div>
    </main>
</template>

<script>
import axios from 'axios'
import SiteAuthor from '@/components/AuthorComponent.vue';
import state from '@/state.js'

export default {
    name: 'AuthorsListComponent',
    components:{
        SiteAuthor,
    },
    data(){
        return{
            API_URL: 'https://flynn.boolean.careers/exercises/api/array/music',
            authors: null,
            loading: true,
            error: null,
        };
    },
    methods:{
        callApi(){
            axios
            .get(this.API_URL)
            .then((response) => {
                this.authors = response.data.response;
            })
            .catch((error) => {
                console.error();
                error;
                this.error = 'Loading...'
            });
        },

        timer(){
            setTimeout(() => {
                this.loading = false;
            }, 2500);
        }
    },
    mounted(){
        this.callApi();
        this.timer();
    },
    computed: {
    filterGenre() {
        return this.authors.filter(genre => {
            return genre.genre.toLowerCase().includes(state.selectGenre.toLowerCase())
            })
        },
    },
};
</script>


<style lang="scss" scoped>
main{
    background-color: $bg-main;

    
}
</style>