<template>
  <b-nav-item-dropdown v-if="$strapi.user" :text="$strapi.user.username">
    <b-dropdown-item to="/user">My Info</b-dropdown-item>

    <b-dropdown-divider />
    <b-dropdown-item to="/" @click="$strapi.logout()">Logout</b-dropdown-item>
  </b-nav-item-dropdown>
  <b-nav-item v-else :active="$route.path === '/login'" to="/login"
    >Login</b-nav-item
  >
</template>

<script>
export default {}
</script>
