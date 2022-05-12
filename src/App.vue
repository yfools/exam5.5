<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </nav>
  <router-view />
</template>
<script>
export default {
  data() {
    return {};
  },

  mounted() {
    let xhr = new XMLHttpRequest();
    xhr.open("GET", "http://www.baidu.com");
    xhr.send();
    this.screenChange();
  },

  methods: {
    screenChange() {
      var mql = window.matchMedia("(orientation: portrait)");
      function onMatchMeidaChange(mql) {
        if (mql.matches) {
          // 竖屏
          console.log('shu')
        } else {
          // 横屏
          console.log('heng')
        }
      }
      onMatchMeidaChange(mql);
      mql.addListener(onMatchMeidaChange);
    },
  },
};
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
