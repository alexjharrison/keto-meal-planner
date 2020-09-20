<template>
  <main>
    <div id="login-box">
      <h1>Login</h1>
      <b-form class="mt-3" @submit.prevent="login">
        <label for="username">Username or Email</label>
        <b-form-input id="username" v-model="identifier" />
        <label for="password">Password</label>
        <b-form-input id="password" v-model="password" type="password" />
        <b-button type="submit" variant="primary">Submit</b-button>
        <b-alert
          :show="Boolean(errorMessage)"
          class="mt-3"
          variant="warning"
          dismissible
          @dismissed="errorMessage = null"
          >{{ errorMessage }}</b-alert
        >
      </b-form>
    </div>
  </main>
</template>

<script>
export default {
  data() {
    return {
      identifier: '',
      password: '',
      errorMessage: null,
    }
  },
  methods: {
    login() {
      this.$strapi
        .login({
          identifier: this.identifier,
          password: this.password,
        })
        .then(res => {
          this.$router.push('/')
        })
        .catch(err => {
          this.errorMessage = err.message
        })
    },
  },
}
</script>

<style lang="scss" scoped>
#login-box {
  max-width: 400px;
  margin: auto;
  form > *:not(label) {
    margin-bottom: 12px;
  }
}
</style>
