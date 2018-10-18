<template>
<div class="">
    {{character}}
</div>
</template>

<script>
export default {
  data() {
    return {
      character: {}
    };
  },
  methods: {
    fetchCharacter() {
      fetch("https://swapi.co/api/people/1", {
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
    this.fetchCharacter();
  }
};
</script>