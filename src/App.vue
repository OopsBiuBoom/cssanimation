<template>
  <div id="app">
    <div class="container">
      <div class="box"><Animation1/></div>
      <div class="box"><Animation2/></div>
    </div>
  </div>

</template>

<style>
  body {
    background-color: black;
    margin: 0;
    padding: 0;
    
  }  

  .container {
    display: flex;
    display: -webkit-flex;
    justify-content: flex-start;
    margin: 10px;
  }

  .box {
    margin: 10px;
  }

</style>

<script>
import Animation1 from './components/Animation1'
import Animation2 from './components/Animation2'


export default {
  name: 'App',
  components: {
    Animation1,
    Animation2
  }
}
</script>
