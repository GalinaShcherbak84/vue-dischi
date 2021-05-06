<template>
    <div class="cont">
        <div class="albums">
            <Card v-for = "(album, index) in albums" :key ='index' :info ="album"/>
        </div>
    </div>
</template>

<script>
import Card from'@/components/Card.vue';
import axios from 'axios';
export default {
    name:'Main',
    components: {
        Card,
    },
    data(){
        return{
            apiURL:'https://flynn.boolean.careers/exercises/api/array/music',
            albums:[],
            loading:true,
        }
    },
    created(){
        this.getAlbums();
    },
    methods:{
        getAlbums(){
            axios.get(this.apiURL)
            .then(res=>{
                console.log(res.data.response);
                this.albums = res.data.response;
                this.loading = false;
            })
            .catch(err=>{
                console.log('Errore',err);
            })
        }
    },
}
</script>

<style scoped lang="scss">
@import'@/styles/vars';
    .cont{
        background:$mycolor;
        .albums{
            width: 80%;
            margin:0 auto;
            display: flex;
            flex-wrap: wrap;
            justify-content:center;
            align-items: center;
            padding: 30px 0 40px;
        }
    }
</style>