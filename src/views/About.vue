<template>
  <div id="about">
    <div>
      <F2 v-for="(qa, index) in about_QandA" :key=index v-bind:QandA="qa"></F2>
    </div>
  </div>
</template>

<script>
import F2 from "@/components/F2.vue";

export default {
  name: 'About',
  components: {
    F2
  },
  data: function() {
    return {
      about_QandA: []
    }
  },
  created() {
    this.axios.get('/data/about.json').then(res => {
      this.about_QandA = res.data.about;
    });
  }
}
</script>
