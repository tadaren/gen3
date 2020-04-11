<template>
  <div id="f2">
    <h2>{{ QandA.question }}</h2>
    <p v-html="QandA.answer"></p>
  </div>
</template>

<script>
export default {
  name: 'F2',
  props: [
    'QandA'
  ]
}
</script>