<template>
  <div>
    <h1>User</h1>
    <b-button variant="primary" to="/" @click="$strapi.logout()"
      >Logout</b-button
    >
  </div>
</template>

<script>
export default {}
</script>
