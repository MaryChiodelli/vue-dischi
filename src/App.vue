<template>
  <div id="app">
    <MainHeader @searchAuthor="getSearchedAutor" @search="onSearch" />
    <MainContent :genre="search" :author="searchedAutor" />
  </div>
</template>

<script>
import MainHeader from './components/MainHeader.vue';
import MainContent from './components/MainContent.vue';

export default {
  name: 'App',
  components: {
    MainHeader,
    MainContent
  },
  data() {
    return {
      search: '',
      searchedAutor: ''
    }
  },
  methods: {
    onSearch(data) {
      console.log(data);
      this.search = data;
    },
    getSearchedAutor(data) {
      this.searchedAutor = data
    }
  }
}
</script>

<style lang="scss">
  @import './styles/index.scss';
</style>
