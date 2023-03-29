<script>

export default {

  name: "CardItem",

  data() {
    return {
    }

  },

  props: {
    card: Object,
  },

}
</script>

<template>
  <div class="card">
    <img :src="card.card_images[0].image_url_small" alt="">
  </div>
</template>

<style lang="scss" scoped>
.card {
  display: flex;
  flex-direction: column;
  margin-bottom: 2em;

  img {
    width: 200px;
    height: auto;
  }

}
</style>