<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <transition name="fade">
      <router-view v-if="show" class="view"/>
    </transition>
  </div>
</template>
<script>
export default {
  name: 'App',
  data () {
    return {
      show: false
    }
  },
  mounted () {
    this.show = true
  },
  beforeDestroy () {
    this.show = false
  }
}
</script>>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
.fade-enter-active,
.fade-leave-active {
  transition: all 0.5s linear;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
  transform: translateX(-100px);
}
.view{
  position: fixed;
  top: 200px;
  left: 40%;
  /* transform: translateX(-50%); */
}
</style>
