<script>
import axios from "axios"
import HorsesIndex from "./HorsesIndex.vue"


export default {
  components: {
    HorsesIndex,
  },

  methods: {
    getStuff: function() {
      console.log("getting some Horses!");
      axios.get("http://localhost:3000/horses.json").then(response => {
        console.log(response.data);
        this.horses = response.data; 
      })
    }
  },
  data: function () {
    return {
      horses: []
    }
  },
}
</script>

<template>
  <main>
    <h1>Welcome to Vue!</h1>
    <HorsesIndex />
    {{ horses }}
    <button v-on:click="getStuff" id="BRB">BIG RED BUTTON</button>
  </main>
</template>

<style>
#BRB {
  color: red;
}
</style>