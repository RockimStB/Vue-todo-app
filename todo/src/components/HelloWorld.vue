<template>
  <div class="hello">
    <link rel="stylesheet" href="/build/tailwind.css">
    <h1 class="text-4xl font-bold text-center text-blue-500">{{ msg }}</h1>
    
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
