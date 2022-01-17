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
   head() {
    return {
      title: "Henri-dev | Blog : Tous les articles",
      meta: [
        {
          hid: `description`,
          name: "description",
          content:
            "Let IT change your life"
        },
        {
          hid: `keywords`,
          name: "keywords",
          keywords: "Blog, Logiciel, SiteWeb, , developpement web, mobile, fullstack, python, django, github, nuxtjs, vuejs, kotlin, php"
        }
      ]
    };
    },
};
</script>
