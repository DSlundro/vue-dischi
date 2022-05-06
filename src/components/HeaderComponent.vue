<template>
    <header>
        <div class="row m-0">
            <div class="col-2">
                <SiteLogo />
            </div>

            <div class="col-10 d-flex justify-content-end align-items-center pe-5">
                <GenreSelector v-model="selectGenre" @changeSelectGenre="changeStateGenre" />
            </div>
        </div>
    </header>
</template>

<script>
import SiteLogo from '@/components/LogoComponent.vue'
import GenreSelector from '@/components/GenreSelector.vue'
import state from '@/state.js'

export default{
    components:{
        SiteLogo,
        GenreSelector,
    },
    data(){
        return{
            selectGenre: '',
        }
    },
    methods:{
        changeStateGenre(){
            console.log(this.selectGenre);
            state.selectGenre = this.selectGenre;
        },
    },
    computed: '',
}
</script>

<style lang="scss" scoped>
    header{
        background-color: $bg-header;
        }
</style>
