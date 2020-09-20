<template>
  <div>
    <h1>
      User
      <b-button variant="primary" to="/" @click="$strapi.logout()"
        >Logout</b-button
      >
    </h1>

    <p>{{ $strapi.user }}</p>
  </div>
</template>

<script>
export default {}
</script>
