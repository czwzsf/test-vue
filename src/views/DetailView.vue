<template>
  <div>
    <h1>详情页: {{ id }}</h1>
  </div>
</template>

<script>
export default {
  name: "DetailView",
  created() {
    this.id = this.$route.params.id
  },
  data() {
    return {
      id: ' '
    }
  },
  watch: {
    $route(to, from) {
      console.log('to', to)
      console.log('from', from)
      this.id = this.$route.params.id
    }
  }
  // 写法2
  // watch: {
  //   $route() {
  //     this.id = this.$route.params.id
  //   }
  // }
}
</script>

<style scoped>

</style>
