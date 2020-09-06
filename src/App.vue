<template>
    <div id="app">
        <h1>Hello world</h1>
        <tabs>
            <tab label="用户管理">用户管理 content</tab>
            <tab label="配置管理">配置管理 content</tab>
        </tabs>
    </div>
</template>

<script>
  /* eslint-disable */
  import Tabs from './components/tabs/tabs'
  import Tab from './components/tabs/tab'

  export default {
    name: 'App',
    components: {
      Tabs,
      Tab
    }
  }
</script>

<style>
    #app {
        font-family: Avenir, Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }
</style>
