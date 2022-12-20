<template>
  <b-navbar class="is-spaced container" 
  
   shadow fixed-top >
    <template #brand>
      <b-navbar-item tag="router-link" :to="{ path: '/' }">
        <!-- <img
          src="./../../assets/logo.png"
          alt="Imagination beyond compréhension"
        /> -->Kreativ Inc
      </b-navbar-item>
    </template>
    <template #end>
      <b-navbar-item>
        <nuxt-link to="/">Solutions</nuxt-link>
      
      </b-navbar-item>
      <b-navbar-item>
        <nuxt-link to="/work">Blog</nuxt-link>
      </b-navbar-item>
      <b-navbar-item >
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
  color: #393357;
}
a.nuxt-link-exact-active {
  color: #393357;
}
</style>
