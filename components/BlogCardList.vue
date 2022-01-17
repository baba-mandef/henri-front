<template>
  <div class="hero-body blog-hero" v-if="loaded">
    <div class="columns" v-for="post in posts" :key="post.id">
      <div class="column is-4">
        <div
          class="blog-prev-img"
          v-bind:style="{
            'background-image': 'url(' + post.banner + ')',
          }"
        ></div>
      </div>
      <div class="column">
        <div class="">
          <hr />
          <small class="is-uppercase">
            <span
              ><b-icon style="color: #2BABE2" icon="calendar" size="is-small">
              </b-icon>
            </span>
            {{ new Date(post.created_at) | dateFormat("DD MMM YYYY") }} |
            <span
              ><b-icon style="color: #2BABE2" icon="folder" size="is-small">
              </b-icon>
            </span>
            {{ post.category }} |
            <span
              ><b-icon style="color: #2BABE2" icon="eye" size="is-small">
              </b-icon>
            </span>
            {{ post.view }}</small
          >
        </div>
        <hr />
        <div>
          <p class="subtitle is-size-6 is-uppercase">
            {{ post.title }}
          </p>

          <nuxt-link
            :to="{
              path: 'blog/post',
              query: { slug: '' + post.slug + '' },
            }"
          >
            <div class="buttons">
              <b-button type="is-primary" expanded outlined>
                <span style="color: black">Lire</span></b-button
              >
            </div>
          </nuxt-link>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
import axios from "axios";
export default {
  data() {
    return {
      loaded: false,
      posts: [],
    };
  },
  methods: {
    snackbar() {
      this.$buefy.snackbar.open({
        duration: 15000,
        message:
          "Le contenu de la page n'est pas entierement chargé. Veuillez verifier votre connexion internet",
        type: "is-danger",
        position: "is-bottom-right",
        actionText: "Rafraîchir",
        queue: false,
        onAction: () => {
          location.reload();
        },
      });
    },
  },

  created() {
    axios
      .get(this.$axios.defaults.baseURL+"/api/v1/blog/post")
      .then((response) => {
        this.posts = response.data;
        this.loaded = true;
      })
      .catch((error) => {
        this.snackbar();
        console.log(error);
      });
  },
};
</script>

<style>
.blog-prev {
  /*  border: solid 1px #2BABE2; */
  border-radius: 2%;
  margin: 5px;
}
@media screen and (min-width: 768px) {
  .blog-prev {
    /*  border: solid 1px #2BABE2; */
    border-radius: 2%;
    margin: 5px;
  }
}
.blog-prev-img {
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;

  height: 215px;
  border: solid 1px #2BABE2;
}
.center {
  margin: 0;

  position: absolute;
  top: 50%;
  left: 50%;
  -ms-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
}

.blog-prev {
  margin: 15px;
}
</style>

