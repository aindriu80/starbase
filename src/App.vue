 

<template>
<div id="app">
    <h3>{{title}}</h3>
    <button class="btn btn-primary" @click="fetchCharacter">Test Fetch Character</button>
</div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      title: "Generate Your Team"
    };
  },
  methods: {
    fetchCharacter() {
      fetch("http://swapi.com/api/people", {
        mode: "no-cors",
        method: "GET"
      });
      // .then(response => response.json())
      // .then(json => console.log(json));
      axios
        .get("http://swapi.com/api/people")
        .then(json => console.log(json))
        .catch(response => console.log(response));
    }
  }
};
</script>