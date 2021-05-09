<template>
    <div class="cont">
        <div class="select">
            <Select @valueChange = "musicGenre" />
        </div>
        
        <div  class="albums">
            <Card v-for = "(album, index) in filteredAlbums" :key ='index' :info ="album"/>
        </div>
    </div>
</template>

<script>
import Card from'@/components/Card.vue';
import Select from'@/components/Select.vue';
import axios from 'axios';
export default {
    name:'Main',
    components: {
        Card,
        Select,
    },
    data(){
        return{
            apiURL:'https://flynn.boolean.careers/exercises/api/array/music',
            albums:[],
            filteredAlbums:[],
            loading:true,
            fitro:'',
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
        },
        musicGenre(text){
            this.filtro = text;
            console.log('cambio!',text);
            this.filteredAlbums = this.albums.filter(item=>{
                if(text===''){
                    return this.albums;
                }else if(text==='pop'){
                    return item.genre==='Pop'
                }else if(text==='jazz'){
                    return item.genre==='Jazz'
                }else if(text==='rock'){
                    return item.genre ==='Rock'
                }else if(text==='metal'){
                    return item.genre ==='Metal'
                }else if(text==='all'){
                    return this.albums
                }
            });
        },
    },
}
</script>

<style scoped lang="scss">
@import'@/styles/vars';
    .cont{
        background:$mycolor;
        height: calc(100vh - 50px);
        overflow: auto;
        .select{
            text-align: center;
            padding-top:20px;
        }
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