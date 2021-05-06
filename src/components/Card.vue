<template>
  <div class="container">
      <div class="img">
          <img :src="info.poster" :alt="info.title">
      </div>
      <h4>{{info.title}}</h4>
      <p>{{info.author}}</p>
      <p>{{info.year}}</p>
      <p class="sm">{{info.genre}}</p>
  </div>
</template>

<script>
export default {
    name:'Card',
    props:['info'],
}
</script>

<style scoped lang="scss">
    @import'@/styles/vars';
    .container{
        color:white;
        width: 150px;
        height: 280px;
        background-color:#2e3a46;
        text-align: center;
        margin: 10px;
        padding:10px;
        .img{
            width: 100%;
            height: 150px;
            img{
                width: 100%;
            }
        }
        p{
            color:gray;
            font-size: 14px;
            margin:8px 0;
        }
        .sm{
            font-size: 12px;
            color:white;
            margin:4px 0;
        }
    }

</style>