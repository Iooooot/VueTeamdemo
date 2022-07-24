<template>
  <div>
    <echartsPage></echartsPage>
    <table-page-vue></table-page-vue>
  </div>

</template>

<script>
import echartsPage from "./views/EchartsPage.vue"
import TablePageVue from "./views/TablePage";
export default {
  components:{
    echartsPage,
    TablePageVue
}
}
</script>

<style>

</style>
