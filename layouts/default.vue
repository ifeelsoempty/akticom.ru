<template>
  <div>
    <iframe src="https://calendar.google.com/calendar/embed?height=600&amp;wkst=1&amp;bgcolor=%23ffffff&amp;ctz=Europe%2FMoscow&amp;src=b245YmV1aGtlMmhxaTFxbXQ1MTVwaTNmMnNAZ3JvdXAuY2FsZW5kYXIuZ29vZ2xlLmNvbQ&amp;color=%234285F4&amp;mode=WEEK&amp;showPrint=0&amp;showTabs=0&amp;showCalendars=0&amp;showTz=1" style="border:solid 1px #777" width="800" height="600" frameborder="0" scrolling="no"></iframe>
    <!-- <Header />
    <Nuxt />
    <CustomCursor /> -->
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