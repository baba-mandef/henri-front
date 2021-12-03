<template>
  <div class="column">
    <div class="card">
      <header class="card-header">
        <p class="card-header-title has-text-black is-size-6">
          {{ title }}
         
           <b-icon
            :icon="icon"
            size="is-small"
            type="is-primary"
            
          />
        </p>
      </header>
      <div class="card-content">
        <div class="content has-text-centered">
         
            <slot />
         
        </div>
      </div>
      <footer class="card-footer">
        <div class="card-footer-item">
         
        </div>
      </footer>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true
    },
    icon: {
      type: String,
      required: true
    }
  }
}
</script>

<style>

</style>
