<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <F1 v-if="test" v-bind:d="test"></F1>
    <div>
      <F2 v-for="(qa, index) in test2" :key=index v-bind:QandA="qa"></F2>
    </div>
    <div>
      <F3 v-for="(concurs, index) in test3" :key=index v-bind:concurs="concurs"></F3>
    </div>
  </div>
</template>

<script>
import F1 from './components/F1.vue'
import F2 from './components/F2.vue'
import F3 from './components/F3.vue'

export default {
  name: 'App',
  components: {
    F1,
    F2,
    F3
  },
  data() {
    return {
      test: null,
      test2: [],
      test3: [],
    }
  },
  created() {
    this.axios.get('/data/test.json').then(res => {
      this.test = res.data;
    });
    this.axios.get('/data/test2.json').then(res => {
      this.test2 = res.data.about;
    });
    this.axios.get('/data/test3.json').then(res => {
      this.test3 = res.data.concurs;
    });
  },
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
