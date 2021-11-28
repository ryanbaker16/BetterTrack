<template>
  <div class="root">
    <div class="wrapper-mains">
        <step-progress :length="4"></step-progress>
    </div>
  </div>
</template>
<script>
import stepProgress from './PrizesSlider'
export default {
  components:{
    stepProgress
  }
}
</script>
(html comment removed:  Add "scoped" attribute to limit CSS to this component only )
<style scoped>
.wrapper-mains{
  width: 561px;
    height: auto;
    background: white;
    text-align: center;
    margin: auto;
    padding: 100px 47px 20px 61px;
}
.textarea{
    display: block;
    width: 100%;
    height: 70px;
    border-radius: 5px;
}
</style>