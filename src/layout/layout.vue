<template>
  <div class="layout" :class="layoutClass">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "g-layout",
  data () {
    return {
      layoutClass: { hasSider: false }
    }
  },
  mounted () {
    this.$children.forEach((vm) => {
      if (vm.$options.name === 'g-side') {
        this.layoutClass.hasSider = true
      }
    })

  }
}
</script>

<style lang="scss" scoped>
.layout {
  display: flex;
  flex-grow: 1;
  flex-direction: column;
  &.hasSider {
    flex-direction: row;
  }
}
</style>
