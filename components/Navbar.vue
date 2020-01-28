<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <nuxt-link class="navbar-brand" to="/">Nuxt SSR</nuxt-link>


    <div class="collapse navbar-collapse">
      <ul class="navbar-nav mr-auto">

        <li class="nav-item">
          <nuxt-link exact no-prefetch active-class="active" class="nav-link" to="/">
            Home
            <span class="sr-only">(current)</span>
          </nuxt-link>
        </li>

        <li class="nav-item">
          <nuxt-link active-class="active" class="nav-link" to="/about">
            About
          </nuxt-link>
        </li>

        <li class="nav-item">
          <nuxt-link active-class="active" class="nav-link" to="/users">
            Users
          </nuxt-link>
        </li>

        <li class="nav-item" v-if="!hasToken">
          <nuxt-link active-class="active" class="nav-link" to="/login">
            Login
          </nuxt-link>
        </li>

        <li class="nav-item" v-else>
          <a @click.prevent="logout" class="nav-link" href="#">
            Logout
          </a>
        </li>

      </ul>
      <form class="form-inline my-2 my-lg-0">
        <button class="enter btn my-2 my-sm-0" type="submit">Вход или регистрация</button>
      </form>
    </div>
  </nav>
</template>

<script>
  export default {
    name: "Navbar",
    methods: {
      logout() {
        this.$store.dispatch('logout')
        this.$router.push('/login')
      }
    },
    computed: {
      hasToken() {
        return this.$store.getters.hasToken;
      }
    },
  }
</script>

<style scoped>
  .active {
    color: chocolate !important;
  }

  .enter {
    font-weight: 600;
    font-size: 20px;
    line-height: 24px;
    padding: 21px 34px;
    background-color: #2F80F3;
  }
</style>
