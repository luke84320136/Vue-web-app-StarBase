<template>
  <div id="app">
    <h1>{{title}}</h1>
    <div class="col-md-12">
      <Character
      v-for= "(id, index) in initial_ids"
      :id= "id"
      key="index"
      />
    </div>
  </div>
</template>

<script>
import Character from './components/Character.vue'
export default {
  name: 'app',
  data () {
    return {
      title: '來組隊吧！！！',
      initial_ids: [1, 13, 14]
    }
  },
  components: {
    Character
  }
}
</script>
