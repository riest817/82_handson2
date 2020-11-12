<template lang="html">
  <div class="sample">
    <h1>{{ title }}</h1>
    Hello, I'm {{ name }}!
    <div>
      {{ reverse }}
    </div>
    <div>
      <button type="button" name="button" @click="plus">
        click times: {{ num }}
      </button>
    </div>
    <div :class="['hide', { seven: num === 7 }]">click 7 times</div>
    <div class="slot">
      <slot />
    </div>
    <div>
      <slot name="come" />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: 'Default Title',
    },
  },
  data() {
    return {
      name: 'Yuya SANO',
      num: 0,
    }
  },
  computed: {
    reverse() {
      return this.name.split('').reverse().join('')
    },
  },
  mounted() {
    console.log('mounted')
  },
  methods: {
    plus() {
      this.num++
    },
  },
}
</script>

<style lang="scss" scoped>
.slot {
  color: red;
}

.hide {
  display: none;

  &.seven {
    display: block;
  }
}
</style>
