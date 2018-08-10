<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <div>
      <button
        v-for="tab in tabs"
        v-bind:key="tab.name"
        v-on:click="currentTab = tab"
      >{{ tab.name }}</button>
      <component v-bind:is="currentTab.component" />
    </div>
  </div>
</template>

<script>
let tabs = [
  {
    name: 'Home',
    component: {
      template: '<div>Home component</div>'
    }
  },
  {
    name: 'Posts',
    component: {
      template: '<div>Posts component</div>'
    }
  },
  {
    name: 'Archive',
    component: {
      template: '<div>Archive component</div>'
    }
  }
]

export default {
  name: 'app',
  data () {
    return {
      tabs: tabs,
      currentTab: tabs[0]
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
