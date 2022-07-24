<template>
  <div class="cardsMain" :style="{backgroundImage: `url(${require('../assets/images/'+cardProp.bkName)})`}">
    <img :src="require('../assets/images/'+cardProp.bkBorderName)"  alt="bkImg">
    <div class="cardTitle" :style="{height:cardProp.titleHeight,lineHeight:cardProp.titleHeight,left:cardProp.titleLeft}">
      <span>{{cardProp.title}}</span>
    </div>
    <slot></slot>
  </div>

</template>

<script>
export default {
    props:['cardProp'],
}
</script>

<style lang="scss" scoped>

  .cardsMain{
    position: relative;
    margin-top: 36px;
    padding: 60px 15px 20px 34px;
    width: 966px;
    background-size: 100% 100%;

    img{
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: 1;
    }


    .cardTitle{
      position: absolute;
      left: 28px;
      top: 0;
      padding-left: 24px;
      font-size: 20px;
      letter-spacing: 5px;
      font-weight: 600;
      color: #EE7832;
      width: 128px;
      background-image: url("../assets/images/xyBk.png");

      span{
        border-top: 2px solid #EE7832;
      }

    }
  }
</style>
  
