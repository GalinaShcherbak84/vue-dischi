<template>
  <header>
      <img src="@/assets/logo.png" alt="">
  </header>
</template>

<script>
export default {
    name: 'Header',
}
</script>

<style scoped lang="scss">
@import'@/styles/vars';
    header{
        height: 50px;
        padding-left:10px;
        display: flex;
        justify-content: start;
        align-items: center;
        background: $mycolorLight;
        img{
            width: 30px;
        }
    }
</style>