<template>
  <div>
    <app-header />
    <b-container fluid="xl">
      <nuxt />
    </b-container>
  </div>
</template>

<script>
import AppHeader from '@/components/header/AppHeader'
export default {
  components: { AppHeader },
  async mounted() {
    await this.$strapi.login({
      identifier: 'alexmon3210',
      password: 'password',
    })
  },
}
</script>

<style>
main {
  @apply contain;
}
</style>
