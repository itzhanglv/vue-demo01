<template>
    <div v-show="visible">
        <slot></slot>
    </div>
</template>

<script>
  export default {
    props: ['label', 'name'],
    data () {
      return {
        visible: false
      }
    },
    mounted () {
      this.$parent.$emit('tab-add', {
        label: this.label,
        name: this.name,
        component: this
      })
    }
  }
</script>