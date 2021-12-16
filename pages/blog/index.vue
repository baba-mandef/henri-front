<template>
  <section class="section">
    <BlogCardList> </BlogCardList>
  </section>
</template>

<script>
import BlogCardList from "../../components/BlogCardList.vue";
export default {
  layout: "blog",
  components: { BlogCardList },
};
</script>
