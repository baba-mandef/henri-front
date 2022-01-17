<template>
  <section class="section">
    <section class="hero">
      <div class="hero-body">
        <div class="container is-max-desktop" v-if="loaded">
          <div v-for="work in works" :key="work.id">
            <h3 class="title is-3 has-text-centered">
              {{ work.name }}
            </h3>
            <div
              class="has-text-centered"
              style="margin-top: 50px; margin-bottom: 60px"
            >
              <img :src="work.banner" alt="Banner" />
            </div>
            <div class="container has-text-justified">
              <p v-html="work.body"></p>
            </div>

            <hr />
            <small class="is-uppercase">
              <span
                ><b-icon
                  style="color: #2BABE2"
                  icon="calendar"
                  size="is-small"
                >
                </b-icon>
              </span>
              {{ new Date(work.created_at) | dateFormat("DD MMM YYYY") }}
            </small>
          </div>
          <hr />
        </div>

        <div
          class="container is-max-desktop"
          v-if="!loaded"
          style="margin-bottom: 50px"
        >
          <p>
            <b-skeleton active></b-skeleton>
            <b-skeleton height="200px"></b-skeleton>
            <b-skeleton active :count="6"></b-skeleton>
          </p>
        </div>

      
      </div>
    </section>
  </section>
</template>

<script>
import axios from "axios";

export default {
  layout: "work",

  data() {
    return {
      works: [],
      pk: null,
      loaded: false,
      
    };
  },

   /*head() {
    return {
      title: "Henri-dev | Projects : "+this.works[0]['name'],
      meta: [
      
        {
          hid: `keywords`,
          name: "keywords",
          keywords: "Projets, Logiciel, SiteWeb, , developpement web, mobile, fullstack, python, django, github, nuxtjs, vuejs, kotlin, php"
        },

        // FACEBOOK META INTEGRATION
        {
          hid: `og:title`,
          name: "og:title",
          content: this.works[0]['title']
        },
         {
          hid: `og:url`,
          name: "og:url",
          content: 'htpps://henri-dev.com/blog/post?slug='+this.works[0]['slug']
        },
         {
          hid: `og:description`,
          name: "og:description",
          content: 'Imagination beyond comprehension.'
        },
         {
          hid: `og:image`,
          name: "og:image",
          content: this.works[0]['banner']
        },

        //TWITTER META INTEGRATION

         {
          hid: `twitter:title`,
          name: "twitter:title",
          content: this.works[0]['title']
        },
         {
          hid: `twitter:url`,
          name: "twitter:url",
          content: 'htpps://henri-dev.com/blog/post?slug='+this.works[0]['slug']
        },
      
         {
          hid: `twitter:image`,
          name: "twitter:image",
          content: this.works[0]['banner']
        },

         {
          hid: `twitter:card`,
          name: "twitter:card",
          content:'summary_larhe_image'
        },

      ]
    };
    },*/

  methods: {
    snackbar() {
      this.$buefy.snackbar.open({
        duration: 10000,
        message:
          "Le contenu de la page n'est pas entierement chargé. Veuillez verifier votre connexion internet",
        type: "is-danger",
        position: "is-bottom-right",
        actionText: "Rafraîchir",
        queue: false,
        onAction: () => {
          this.$router.go();
        },
      });
    },

    
  },
  created() {
    var url =
      this.$axios.defaults.baseURL+"/api/v1/work?slug=" +
      this.$route.query.slug;

    axios
      .get(url)
      .then((response) => {
        this.works = response.data;
        var post_pk = response.data[0]["id"];
        this.pk = post_pk;
        this.loaded=true;
      })
      .catch((error) => {
        this.snackbar();
        console.log(error);
      });
  },
};
</script>


<style>
.comment {
  margin-bottom: 30px;
  background-color: rgb(230, 230, 230);
  border-radius: 10px;
}
</style>
