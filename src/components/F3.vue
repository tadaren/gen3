<template>
  <div id="f3">
    <h2>{{ concurs.year }}年</h2>
    <p>
      奈良県大会 <span :class="{ gold : isGold }">{{ concurs.award }}</span>
      <span v-if="concurs.isRepresent"> & 代表</span>
    </p>
    <p v-for="(c, i) in concurs.next" :key="i">
      {{ c.competitionName }} {{ c.award }}<span v-if="c.isRepresent"> & 代表</span>
    </p>
    <p v-if="concurs.aSetPiece">曲名 {{ concurs.aSetPiece }} ／ {{ concurs.freeProgram }}</p>
    <p v-if="concurs.musicTitle">曲名 {{ concurs.musicTitle }}</p>
  </div>
</template>

<script>
export default {
  name: 'F3',
  props: {
    concurs: Object
  },
  computed: {
    isGold: function() {
      return this.concurs.award === "金賞";
    }
  }
}
</script>

<style scoped>
.gold {
  color : #c06e02
}
</style>
