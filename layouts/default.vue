<template>
  <div id="app">
    <img src="~/assets/logo.png">
    <nuxt />
  </div>
</template>

<script>
import * as Auth0 from 'auth0-web'

export default {
  name: 'App',
  created () {
    Auth0.configure({
      domain: 'my-nuxt-app.auth0.com',
      clientID: 'z6Wb7SucaAlat31wzYOY3MEIC31y7vQR',
      audience: 'https://micro-blog-app',
      redirectUri: 'http://localhost:8080/callback',
      responseType: 'token id_token',
      scope: 'openid profile'
    })
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
