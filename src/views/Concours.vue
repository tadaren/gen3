<template>
  <div id="concours">
    <div>
      <h2>吹奏楽コンクール実績</h2>
      <F3 v-for="(c, index) in concours" :key=index v-bind:concurs="c"></F3>
    </div>
    <div>
      <h2>アンサンブルコンテスト</h2>
      <F3 v-for="(e, index) in ensemble" :key=index v-bind:concurs="e"></F3>
    </div>
  </div>
</template>

<script>
import F3 from '@/components/F3.vue'

export default {
  name: 'Concours',
  components: {
    F3
  },
  data() {
    return {
      concours: [],
      ensemble: [],
    }
  },
  created() {
    this.axios.get('/data/concours.json').then(res => {
      this.concours = res.data.concours;
    });
    this.axios.get('/data/ensemble.json').then(res => {
      this.ensemble = res.data.ensemble;
    });
  }
}
</script>
