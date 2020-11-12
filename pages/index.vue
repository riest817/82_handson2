<template>
  <div>
    <Sample :title="indexTitle">
      Hello Slot!
      <div slot="come">name slot</div>
    </Sample>
    <nuxt-link to="/about">ABOUT</nuxt-link>
  </div>
</template>

<script>
import Sample from '~/components/Sample.vue'

export default {
  components: {
    Sample,
  },
  data() {
    return {
      indexTitle: 'Nuxt.js data',
    }
  },
}
</script>

<script>
export default {}
</script>

<style></style>
