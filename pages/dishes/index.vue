<template>
  <div>
    <h1>Dishes</h1>
    <ul>
      <li v-for="dish in dishes" :key="dish.id">{{ dish.name }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  async asyncData({ $strapi }) {
    const dishes = await $strapi.$dishes.find()
    return { dishes }
  },
}
</script>
