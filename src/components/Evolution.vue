<template>
  <div class="evolution">
    <h2>{{title}}</h2>
    <TwentyTwenty :before="from" :after="to" />
    <p>{{text}}</p>
  </div>
</template>

<script>
import TwentyTwenty from 'vue-twentytwenty'

export default {
  components: {
    TwentyTwenty
  },
  props: ['from', 'to', 'text', 'title']
}
</script>

<style>
.evolution {
  border: 0.5rem solid #4DBA87;
  margin: 1rem;
  overflow: clip;
}
</style>
