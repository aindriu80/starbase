<template>
<div class="" @click="switchCharacter">
    {{character}}
</div>
</template>

<script>
export default {
  props: ["id"],
  data() {
    return {
      character: {}
    };
  },
  methods: {
    fetchCharacter(id) {
      fetch(`https://swapi.co/api/people/${id}`, {
        // mode: "no-cors",
        method: "GET"
      })
        //   axios
        // .get("http://swapi.com/api/people")
        .then(response => response.json())
        .then(json => (this.character = json));
      // .catch(response => console.log(response));
    },
    switchCharacter() {
      let random_id = Math.floor(Math.random() * 83) + 1;
      this.fetchCharacter(random_id);
    }
  },
  created() {
    this.fetchCharacter(this.id);
  }
};
</script>