<template>
  <div>
    <h1>Components</h1>
    <ul>
      <li v-for="component in components" :key="component.id">
        {{ component.name }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  async asyncData({ $strapi }) {
    const components = await $strapi.$components.find()
    return { components }
  },
}
</script>
