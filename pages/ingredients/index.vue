<template>
  <div>
    <h1>Ingredients</h1>
    <ul>
      <li v-for="ingredient in ingredients" :key="ingredient.id">
        {{ ingredient.name }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  async asyncData({ $strapi }) {
    const ingredients = await $strapi.$ingredients.find()
    // const { ingredients } = await $strapi.graphql({
    //   query: `
    //     query {
    //       ingredients {
    //         id,
    //         name
    //       }
    //     }
    //   `,
    // })
    return { ingredients }
  },
}
</script>
