<template>
  <main>
    <LoadingComponent v-if="productList.length === 0" />
    <div class="container">
      {{ uniqueGenreTypes }} - {{ uniqueAuthorNames }}
      <div class="row">
        <div class="col" v-for="(product, index) in filteredSongs" :key="index">
          <CardComponent :info="product" />
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
    props: {
      author: {
        type: String,
        default: ''
      },
      genre: {
        type: String,
        default: ''
      }
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
          this.productList = res.data.response;
        });
    },
    computed: {
      filteredSongs() {
        return this.productList.filter((product) => {
          return (product.genre.includes(this.genre) && product.author.includes(this.author));
        });
      },
      uniqueGenreTypes() {
        const types = [];
        this.productList.forEach((product) => {
          if (!types.includes(product.genre)) {
            types.push(product.genre);
          }
        });
        return types;
      },
      uniqueAuthorNames() {
        const authors = [];
        this.productList.forEach((product) => {
          if (!authors.includes(product.author)) {
            authors.push(product.author);
          }
        });
        return authors;
      }
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