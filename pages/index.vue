<template>
  <div class="container">
    <h1>Ciao</h1>
    <p>
      <nuxt-link to="/product">Product Page</nuxt-link>
    </p>
  </div>
</template>

<script>
import AppLogo from '~/components/AppLogo.vue'

export default {
  components: {
  }
}
</script>

<style>
  .container {
    font-family: 'Quicksand', 'Source Sans Pro', apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
    padding: 3.5rem;
  }
</style>
