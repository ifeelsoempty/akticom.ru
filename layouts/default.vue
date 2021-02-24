<template>
  <div>
    <Header />
    <Nuxt />
    <CustomCursor />
  </div>
</template>

<script>
export default {
  components: {
    // Cursor, 
  },
  async mounted() {
    document.body.classList.add('has-dom-loaded')
  }
}
</script>

<style>

</style>