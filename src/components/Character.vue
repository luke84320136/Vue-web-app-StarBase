<template>
  <div class="col-md-4" @click= "switchCharacter">
    <div class="character-card">
      <div class="card-block">
        <h4 class= "card-title">{{character.name}}</h4>
         <p class= "card-text">身高: {{character.height}}公分</p>
         <p class= "card-text">體重: {{character.mass}}公斤</p>
         <p class= "card-text">髮色: {{character.hair_color}}</p>
         <p clas= "card-text">眼睛的顏色: {{character.eye_color}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['id'],
  data(){
    return{
      character: {}
    }
  },
  methods:{
    fetchCharacter(id) {
      fetch(`http://swapi.co/api/people/${id}`, {
        method: 'GET'
      })
      .then(response => response.json())
      .then(json => this.character = json)
    },
    switchCharacter() {
      let random_id = Math.floor(Math.random() *83) +1
      this.fetchCharacter(random_id)
    }
  },
  created() {
    this.fetchCharacter(this.id)
  }
}
</script>
