<template>
    <div id="app">
        <button @click="visible2=true"> ccc </button>
        <transition name="van-slide-right">
           <index-bar-popup v-show="visible2" />
        </transition>
        <transition name="van-slide-right">
           <index-bar v-show="visible1" />
        </transition>
    </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import IndexBar from './components/indexBar.vue'
import IndexBarPopup from './components/indexBarPopup.vue'


export default {
  name: 'app',
  components: {
    HelloWorld,
    IndexBar,
    IndexBarPopup
  },
  data() {
    return {
      visible1: false,
      visible2: false
    }
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
