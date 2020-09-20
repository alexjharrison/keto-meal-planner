<template>
  <b-navbar variant="info" toggleable="md" type="dark">
    <b-container fluid="xl" class="white">
      <b-navbar-brand to="/">Keto Meal Planner</b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav class="ml-auto">
          <b-nav-item
            v-for="page in pages"
            :key="page.name"
            :active="$route.path.startsWith(page.path)"
            :to="page.path"
            >{{ page.name }}</b-nav-item
          >
          <login-box />
        </b-navbar-nav>
      </b-collapse>
    </b-container>
  </b-navbar>
</template>

<script>
import LoginBox from './LoginBox'

export default {
  components: { LoginBox },
  data() {
    const pages = ['ingredients', 'components', 'dishes', 'recipes']
    return {
      pages: pages.map(name => ({
        name: name.charAt(0).toUpperCase() + name.slice(1),
        path: '/' + name,
      })),
    }
  },
}
</script>
