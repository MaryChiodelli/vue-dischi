<template>
  <header>
    <img class="header-logo" src="../assets/logo.png" alt="Spotify logo">
  </header>
</template>

<script>
export default {
  name: 'MainHeader'
}
</script>

<style lang="scss" scoped>
  header {
    padding: 12px 20px;
    background-color: #2E3A46;
  }

  .header-logo {
    width: 46px;
    aspect-ratio: 1 / 1;
  }
</style>