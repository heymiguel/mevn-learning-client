<template>
  <div class="character-creator">
    <h1>character Creator</h1>
    <label for="character-name">Character Name:</label>
    <input type="text" id="character-name" v-model="name" placeholder="Enter a name">
    <label for="professions-list">Character Profession</label>
    <select name="" id="professions-list" v-model="profession">
      <option value="mage">mage</option>
      <option value="thief">thief</option>
      <option value="warrior">warrior</option>
    </select>
    <button v-on:click="postCharacter"> Create Character </button>
  </div>
</template>

<script>
import axios from "axios"
export default {
  name: 'CharacterCreator',
  data: function(){
    return {
      name: null,
      profession: null
    }
  },
  methods:{
    postCharacter: function(){
      axios.post('http://localhost:3000/characters', {
        name: this.name,
        profession: this.profession
      })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
