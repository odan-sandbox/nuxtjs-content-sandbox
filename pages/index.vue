<template>
  <div class="container">
    <h1>{{ index.title }}</h1>
    <nuxt-content class="content" :document="index" />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  async asyncData (app) {
    const index = await app.$content('index').fetch()
    return { index }
  }
})
</script>

<style scoped>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  flex-direction: column;
}

.content {
  display: flex;
}

</style>
