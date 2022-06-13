<template>
  <div class="home-page">
    <h1>Home Page</h1>
    <p>This is the Home Page</p>
    {{ message }}
  </div>
</template>

<script>
export default {
  name: 'HomePage',
  // eslint-disable-next-line space-before-function-paren
  data() {
    return {
      message: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<style>
.home-page {
  padding: 20px;
}
</style>
