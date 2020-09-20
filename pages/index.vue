<template>
  <div>
    <h1>keto-meal-planner</h1>
    <p>{{ $strapi.user }}</p>
    <p>{{ ingredients }}</p>
    <div class="links">
      <a
        href="https://nuxtjs.org/"
        target="_blank"
        rel="noopener noreferrer"
        class="button--green"
      >
        Documentation
      </a>
      <a
        href="https://github.com/nuxt/nuxt.js"
        target="_blank"
        rel="noopener noreferrer"
        class="button--grey"
      >
        GitHub
      </a>
    </div>
  </div>
</template>

<script>
export default {
  async fetch() {
    this.ingredients = await this.$strapi.$ingredients.find()
  },
  data() {
    return {
      ingredients: null,
    }
  },
}
</script>
