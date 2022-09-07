<template>
  <main>
    <div class="container">
      <div class="row">
        <div class="col">
          <CardComponent />
        </div>
      </div>
    </div>
  </main>
</template>

<script>
  import CardComponent from './CardComponent.vue';
  import axios from 'axios';

  export default {
    name: 'MainContent',
    components: {
      CardComponent
    },
    data() {
      return {
        productList: []
      }
    },
    created() {
      axios
        .get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((res) => {
          this.productList.push(...res.data.response);
        });
    }
  }
</script>

<style lang="scss" scoped>
  main {
    padding: 5rem 0;
    background-color: #1E2D3B;
  }
</style>