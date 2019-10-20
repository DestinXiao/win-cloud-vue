<template>
  <div id="app">

    <div class="video" style="position: fixed; top: 0;left: 0;width: 100%;height:100%;z-index: -11" >
      <video id="video" @contextmenu.prevent="" class="video" style="min-width: 100%;height: 100%;object-fit: fill" autoplay="autoplay" loop="loop" src="//qzonestyle.gtimg.cn/qz-proj/wy-pc-v3/static/img/web/top.webm">
      </video>
    </div>
    <Login />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Login from "./components/Login";
export default {
  name: 'app',
  components: {
    Login
  }

}

</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
