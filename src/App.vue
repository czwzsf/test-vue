<template>
  <div id="app">
    <nav>
      <router-link to="/">Home</router-link>
      |
      <router-link to="/about">About</router-link>
      |
      <router-link to="/detail/123/type1">详情1</router-link>
      |
      <router-link :to='"/detail/" + id + "/" + types'>详情2</router-link>
      |
      <router-link :to='{path: "/detail/" + id + "/" + types, query: {name: "abc", sort: "desc"}}'>详情3</router-link>
      |
      <router-link
          :to='{name: "detail-page", params: {id: "abc123", types: "type3"}, query: {name: "abc", sort: "desc"}}'>详情4
      </router-link>
      |
    </nav>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      id: 456,
      types: 'type2'
    }
  },
  methods: {
    goHome() {
      // this.$router.push({name: 'home'})
      // this.$router.push({name: "detail-page", params: {id: "abc123", types: "type3"}, query: {name: "abc", sort: "desc"}})
      // this.$router.go(-1)
      this.$router.replace({name: 'home'})
    }
  },
  components: {
    // HelloWorld
  }
}
</script>
<style lang="less">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
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
