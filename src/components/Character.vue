<template>
<div class="">
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
    }
  },
  created() {
    this.fetchCharacter(this.id);
  }
};
</script>