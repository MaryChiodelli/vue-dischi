<template>
  <div id="app">
    <MainHeader @search="onSearch" />
    <MainContent :genre="search" />
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
      search: ''
    }
  },
  methods: {
    onSearch(data) {
      console.log(data);
      this.search = data;
    }
  }
}
</script>

<style lang="scss">
  @import './styles/index.scss';
</style>
