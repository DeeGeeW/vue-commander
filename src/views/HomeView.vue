<script>
import axios from "axios";
export default {
  data: function () {
    return {
      decks: {},
    };
  },
  created: function () {
    this.indexDecks();
  },
  methods: {
    indexDecks: function () {
      axios.get("/decks").then((response) => {
        console.log("decks index", response);
        this.decks = response.data;
        console.log(this.decks);
      });
    },
  },
};
</script>

<template>
  <div class="home">
    <h1>All decks</h1>
    <div v-for="deck in decks" v-bind:key="deck.id">
      <img v-bind:src="deck.commander" v-bind:alt="deck.commander" />
    </div>
  </div>
</template>

<style></style>
