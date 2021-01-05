<template>
  <div id="app">
    <div id="nav">
    </div>
    <Common-header></Common-header>
    <div class="container"><router-view/></div>
    <Common-footer></Common-footer>
  </div>
</template>
<script>
  import CommonHeader from "./components/CommonHeader";
  import CommonFooter from "./components/CommonFooter";
  export default {
    components:{
      CommonFooter,
      CommonHeader
  }
  }
</script>
<style lang="scss">
.container {
  margin-top: 1rem;
  margin-bottom: 1rem;
}

</style>
