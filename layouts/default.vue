<template>
  <div>
    <app-header />
    <b-container fluid="xl" class="py-4">
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
