<template>
  <div>
    <h1>Recipes</h1>
    <ul>
      <li v-for="recipe in recipes" :key="recipe.id">{{ recipe.name }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  async asyncData({ $strapi }) {
    const recipes = await $strapi.$recipes.find()
    return { recipes }
  },
}
</script>
