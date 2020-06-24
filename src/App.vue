<template>
  <div id="app">
    <Navbar/>
    <router-view/>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'
import Navbar from '@/components/hoc/Navbar.vue'

@Component({
  components: {
    Navbar
  }
})
export default class App extends Vue {
  @Prop() private msg!: string;
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  letter-spacing: 1px;
}
a {
  text-decoration: unset;
  color: inherit;
}
html {
  background-color: #f9f9f9;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  --orange: #F2994A;
  --light-default: #FAFAFA;
}

@media only screen and (min-width: 768px) {
  html {
    margin-top: 50px;
  }
}
</style>
