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
        padding:10px;
        background: $mycolorLight;
        img{
            width: 30px;
        }
    }
</style>