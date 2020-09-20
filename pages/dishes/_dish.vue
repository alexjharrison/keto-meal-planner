<template>
  <div>
    <h1>{{ dish.name }}</h1>
  </div>
</template>

<script>
export default {
  async asyncData({ $strapi, params }) {
    const dish = await $strapi.$dishes.findOne(Number(params.dish))
    return { dish }
  },
}
</script>
