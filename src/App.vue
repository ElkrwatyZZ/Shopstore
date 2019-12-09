<template>
  <div id="app">
    <appheader />
    <serchandsingin />
    <router-view />
  </div>
</template>

<script>
import appheader from '../src/components/global/appheader'
import serchandsingin from '../src/components/global/serchandsingin'
export default {
  name: 'app',
  components: {
    appheader,
    serchandsingin
  }
}
</script>
<style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
