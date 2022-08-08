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
    let name = this.$route.query.name
    console.log('name:', name)
    console.log('sort:', this.$route.query.sort)
    console.log('id:', this.id)
    console.log('types:', this.$route.params.types)

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
