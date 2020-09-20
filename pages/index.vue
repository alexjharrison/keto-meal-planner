<template>
  <div>
    <h1>Keto Meal Planner</h1>
    <h2>Dish of the day</h2>
    <random-dish :dish="dish" />
  </div>
</template>

<script>
import RandomDish from '@/components/home/RandomDish'

export default {
  components: { RandomDish },
  async asyncData({ $strapi, $http }) {
    const count = await $strapi.$dishes.count()
    const randomDishId = Math.ceil(Math.random() * count)
    const dish = await $strapi.$dishes.findOne(randomDishId)
    return { dish }
  },
}
</script>
