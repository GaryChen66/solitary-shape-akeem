<template>
  <div :id="petcard.id" v-on:click="goToDetail()">
    <div class="card w-100 shadow bg-white rounded"></div>
  </div>
</template>

<script>
import _ from "lodash";
import favorite from "./Favorite";

export default {
  props: {},
  components: {
    favorite
  },

  data() {
    return {
      shouldShowCard: false
    };
  },

  mounted() {
    if (this.unavailable) {
      //$(`#${this.petcard.id} .petcard-unavailable`).tooltip();
    }
  },

  computed: {},

  methods: {
    goToDetail: function(event) {
      window.location.href = `/search/s/${this.petcard.id}`;
    }
  }
};
</script>

<style lang="scss" scoped>
.petcard-card {
  min-width: 20%;
  cursor: pointer;
  transition: opacity 0.4s;
  opacity: 0;

  &.showCard {
    opacity: 1;
    transition: opacity 0.4s;
  }
}
</style>
