<template>
  <div id="link">
    <h2>LINK集</h2>
    <div>
      <div v-for="(group, index) in links" :key=index>
        <h3>{{ group.groupName }}</h3>
        <ul>
          <li v-for="(link, index) in group.links" :key=index>
            <a v-bind:href="link.url">{{ link.name }}</a>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Link',
  data: function() {
    return {
      "links": []
    }
  },
  created: function() {
    this.axios.get('/data/links.json').then(res => {
      this.links = res.data.links;
    });
  }
}
</script>
