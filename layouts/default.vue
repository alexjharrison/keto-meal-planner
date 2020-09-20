<template>
  <div>
    <app-header />
    {{ $strapi.user }}
    <b-container fluid="xl">
      <nuxt />
    </b-container>
  </div>
</template>

<script>
import AppHeader from '@/components/header/AppHeader'
import '@/assets/scss/bootstrap.scss'
export default {
  components: { AppHeader },
}
</script>
