<template>
  <section class="section">
    <WorkCardList> </WorkCardList>
  </section>
</template>

<script>
import WorkCardList from "../../components/.old/WorkCardList.vue";
export default {
  layout: "work",
  components: { WorkCardList },
  head() {
    return {
      title: "Henri-dev | Projets : Tous les projets",
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
          keywords: "Projets, Logiciel, SiteWeb, , developpement web, mobile, fullstack, python, django, github, nuxtjs, vuejs, kotlin, php"
        }
      ]
    };
    },
};
</script>
