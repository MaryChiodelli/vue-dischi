<template>
  <main>
    <LoadingComponent v-if="productList.length === 0" />
    <div class="container">
      <div class="row">
        <div class="col" v-for="(product, index) in productList" :key="index">
          <CardComponent :img="product.poster" :author="product.author" :title="product.title" :year="product.year" />
        </div>
      </div>
    </div>
  </main>
</template>

<script>
  import LoadingComponent from './LoadingComponent.vue';
  import CardComponent from './CardComponent.vue';
  import axios from 'axios';

  export default {
    name: 'MainContent',
    components: {
      LoadingComponent,
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
    padding: 5rem 0 3.75rem;
    background-color: #1E2D3B;
  }

  .col {
    margin-bottom: 1.25rem;
  }
</style>