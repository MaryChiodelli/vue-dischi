<template>
  <div class="card">
    <img class="card-img" :src="info.poster" :alt="info.title">
    <h3 class="card-title">{{ info.title }}</h3>
    <div class="card-author">{{ info.author }}</div>
    <div class="card-year">{{ info.year }}</div>
  </div>
</template>

<script>
  export default {
    name: 'CardComponent',
    props: {
      info: Object
    }
  }
</script>

<style lang="scss" scoped>
  .card {
    height: 100%;
    padding: 1.25rem;
    color: #808080;
    text-align: center;

    .card-img {
      width: 100%;
      display: block;
      margin-bottom: 1.25rem;
      aspect-ratio: 1 / 1;
    }

    .card-title {
      margin-bottom: 1rem;
      font-size: 1.5rem;
      line-height: 120%;
      text-transform: uppercase;
      color: white;
    }

    .card-author {
      font-size: 1.25rem;
      line-height: 130%;
    }

    .card-year {
      font-size: 1rem;
      line-height: 100%;
    }
  }
</style>