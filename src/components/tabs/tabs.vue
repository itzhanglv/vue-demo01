<template>
    <div>
        <div class="titles">
            <div class="title"
                 v-for="(tab, idx) in tabs"
                 :key="idx"
                 :class="{selected: idx === selectedIndex}"
                 @click="changeTab(tab, idx)">
                {{tab.label}}
            </div>
        </div>
        <div class="content">
            <slot></slot>
        </div>
    </div>
</template>

<script>
  /* eslint-disable */
  export default {
    props: [],
    data () {
      return {
        tabs: [], // {label, name, component}[]
        tabContent: null,
        selectedIndex: 0
      }
    },
    methods: {
      changeTab (tab, idx) {
        this.selectedIndex = idx
        this.tabs.forEach((tab, index) => {
          if (index === idx) {
            tab.component.visible = true
          } else {
            tab.component.visible = false
          }
        })
      }
    },
    created () {
      this.$on('tab-add', ({label, name, component}) => {
        this.tabs.push({label, name, component})
      })
      // this.$emit('tab-add')
    },
    mounted () {
      if (this.tabs[0]) {
        this.tabs[0].component.visible = true
      }
    }
  }
</script>

<style lang="less">
    .titles {
        display: flex;
        .title {
            border: 1px solid #000;
            width: 100px;
            height: 30px;
            cursor: pointer;
            &:hover {
                background-color: dodgerblue;
            }
            &.selected {
                background-color: deeppink;
            }
        }
    }

    .content {
        background-color: pink;
    }
</style>