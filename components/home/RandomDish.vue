<template>
  <div>
    <h3 class="text-center">
      <n-link :to="`/dishes/${dish.id}`">{{ dish.name }}</n-link>
    </h3>
    <b-img
      v-if="imageUrl"
      class="rounded"
      fluid
      :src="imageUrl"
      :alt="dish.name"
    />
    <small>{{ dish }}</small>
  </div>
</template>

<script>
export default {
  props: { dish: { type: Object, required: true } },
  computed: {
    imageUrl() {
      return this.dish.image[0]?.url
    },
  },
}
</script>
