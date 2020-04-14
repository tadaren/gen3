<template>
  <div id="home">
    <F1 v-if="latest_concerts" v-bind:d="latest_concerts"></F1>
    <Timeline :id="user_id" source-type="profile" :options="{ tweetLimit: '3' }" />
  </div>
</template>

<script>
import F1 from '@/components/F1.vue'
import { Timeline } from 'vue-tweet-embed'

export default {
  name: 'Home',
  components: {
    F1,
    Timeline
  },
  data: function() {
    return {
      latest_concerts: null,
      user_id: "NITNC_Band"
    }
  },
  created() {
    this.axios.get('/data/latest_concerts.json').then(res => {
      this.latest_concerts = res.data;
    });
  }
}

</script>
