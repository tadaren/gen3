<template>
  <div id="concours">
    <div>
      <F3 v-for="(concurs, index) in test3" :key=index v-bind:concurs="concurs"></F3>
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
      test3: [],
    }
  },
  created() {
    this.axios.get('/data/test3.json').then(res => {
      this.test3 = res.data.concurs;
    })
  }
}
</script>
