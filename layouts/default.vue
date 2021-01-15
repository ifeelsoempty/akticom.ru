<template>
  <div>
    <Header />
    <Nuxt />
  </div>
</template>

<script>
export default {
  beforeMount() {
    },
  async mounted() {
    document.body.classList.add('has-dom-loaded')
  }
}
</script>

<style>

</style>