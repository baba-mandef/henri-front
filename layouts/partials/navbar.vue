<template>
  <b-navbar class="is-spaced" wrapper-class="container">
    <template #brand>
      <b-navbar-item tag="router-link" :to="{ path: '/' }">
        <img
          src="./../../assets/logo.png"
          alt="Imagination beyond compréhension"
        />
      </b-navbar-item>
    </template>
    <template #end>
      <b-navbar-item>
        <nuxt-link to="/">Accueil</nuxt-link>
      </b-navbar-item>
      <b-navbar-item>
        <nuxt-link to="/blog">Blog</nuxt-link>
      </b-navbar-item>
      <b-navbar-item>
        <nuxt-link to="/work">Projets</nuxt-link>
      </b-navbar-item>
      <b-navbar-item>
        <nuxt-link to="/service">Services</nuxt-link>
      </b-navbar-item>
    </template>

    <!-- <template #end>
            <b-navbar-item tag="div">
                <div class="buttons">
                    <a class="button is-primary">
                        <strong>Sign up</strong>
                    </a>
                    <a class="button is-light">
                        Log in
                    </a>
                </div>
            </b-navbar-item>
        </template> -->
  </b-navbar>
</template>

<style>
.navbar a {
  font-weight: bold;
  color: white;
}
a.nuxt-link-exact-active {
  color: lightblue;
}
</style>
