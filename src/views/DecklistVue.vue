<script>
import axios from "axios";
export default {
  data: function () {
    return {
      cards: {},
    };
  },
  mounted: function () {
    console.log(this.$route.params.id);
    axios.get(`/decks/${this.$route.params.id}`).then((response) => {
      this.deck = response.data;
      // this.cards = this.deck.cards;
      // console.log(this.cards);
      console.log(this.deck);
    });
  },
};
</script>
