<template>
  <div class="column">
    <div class="card">
      <header class="card-header">
        <p class="card-header-title has-text-black is-size-6">
          <slot name="header"> </slot>
        </p>
      </header>
      <div class="card-content">
        <div class="content has-text-centered">
          <span>
            <slot />
          </span>
        </div>
      </div>
      <footer class="card-footer">
        <div class="card-footer-item"></div>
      </footer>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style>
</style>
