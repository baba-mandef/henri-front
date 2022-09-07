<template>
  <b-navbar class="is-spaced" shadow>
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
        <nuxt-link to="/">Solutions</nuxt-link>
      
      </b-navbar-item>
      <b-navbar-item>
        <nuxt-link to="/work">Blog</nuxt-link>
      </b-navbar-item>
      <b-navbar-item style="border-bottom:3px solid black; border-radius:0px !important; padding: 0%; margin:2%; width: max-content;">
        <nuxt-link to="/blog">Shop</nuxt-link>
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
  color: #2BABE2;
}
a.nuxt-link-exact-active {
  color: #2BABE2;
}
</style>
