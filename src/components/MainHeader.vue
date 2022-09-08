<template>
  <header>
    <img class="header-logo" src="../assets/logo.png" alt="Spotify logo">
    <select v-model="genre" @change="$emit('search', genre)">
      <option value="">Seleziona un genere</option>
      <option>Rock</option>
      <option>Pop</option>
      <option>Jazz</option>
      <option>Metal</option>
    </select>
    <select v-model="autor" @change="$emit('searchAuthor', autor)">
      <option value="">Seleziona un autore</option>
      <option>Bon Jovi</option>
      <option>Queen</option>
      <option>Sting</option>
      <option>Steve Gadd Band</option>
      <option>Iron Maiden</option>
      <option>Eric Clapton</option>
      <option>Deep Purple</option>
      <option>Metallica</option>
      <option>Dave Weckl</option>
      <option>Michael Jacjson</option>
    </select>
  </header>
</template>

<script>
  export default {
    name: 'MainHeader',
    data() {
      return {
        genre: '',
        autor: ''
      }
    }
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