<template>
  <div class="hero-body blog-hero">
    <div v-if="loaded">
      <div
        class="has-text-centered"
        style="margin-top: 15px; margin-bottom: 30px"
      >
        <p class="title is-size-4 is-size-5-mobile" style="padding-bottom: ">
          Articles récents
          <b-icon
            icon="file-document-outline"
            size="#is-small"
            style="color: lightblue"
          ></b-icon>
        </p>
      </div>
      <div class="columns">
        <div class="column is-4 blog-prev" v-for="post in posts" :key="post.id">
          <div
            class="blog-prev-img"
            v-bind:style="{
              'background-image': 'url(' + post.banner + ')',
            }"
          ></div>
          <hr />
          <div class="">
            <small class="is-uppercase">
              <span
                ><b-icon
                  style="color: lightblue"
                  icon="calendar"
                  size="is-small"
                >
                </b-icon>
              </span>
              {{ new Date(post.created_at) | dateFormat("DD MMM YYYY") }} |
              <span
                ><b-icon style="color: lightblue" icon="folder" size="is-small">
                </b-icon>
              </span>
              {{ post.category }} |
              <span
                ><b-icon style="color: lightblue" icon="eye" size="is-small">
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
              ><b-button type="is-primary" expanded outlined>
                <span style="color: black">Lire</span></b-button
              ></nuxt-link
            >
            <div class="buttons"></div>
          </div>
        </div>
      </div>
      <div class="column is-full has-text-centered">
        <p class="title is-size-5">
          <nuxt-link to="/blog" style="color: lightblue"
            >Voir tous les articles
            <span
              ><b-icon
                style="color: lightblue"
                icon="hand-pointing-left"
              ></b-icon></span
          ></nuxt-link>
        </p>
      </div>
    </div>
    <div v-if="!loaded" class="columns">
      <div class="column is-4 blog-prev">
        <p>
          <b-skeleton height="215px" style=""></b-skeleton>

          <b-skeleton active :count="1"></b-skeleton>
          <b-skeleton height="80px" style=""></b-skeleton>
        </p>
      </div>

      <!--   <div class="column is-4 blog-prev">
        <p>
          <b-skeleton height="215px" style=""></b-skeleton>

          <b-skeleton active :count="1"></b-skeleton>
          <b-skeleton height="80px" style=""></b-skeleton>
        </p>
      </div>

       <div class="column is-4 blog-prev">
        <p>
          <b-skeleton height="215px" style=""></b-skeleton>

          <b-skeleton active :count="1"></b-skeleton>
          <b-skeleton height="80px" style=""></b-skeleton>
        </p>
      </div> -->
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

    getLatest(size, payload) {
      let endV = [];

      for (var i = 0; i < size; i++) {
        if (payload[i] == undefined) {
          break;
        } else {
          endV.push(payload[i]);
        }
      }

      return endV;
    },
  },

  created() {
    axios
      .get("http://sadih.herokuapp.com/api/v1/blog/post")
      .then((response) => {
        const data = response.data;
        this.posts = this.getLatest(3, data);
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
  /*  border: solid 1px lightblue; */
  border-radius: 2%;
  margin: 5px;
}
@media screen and (min-width: 768px) {
  .blog-prev {
    /*  border: solid 1px lightblue; */
    border-radius: 2%;
    margin: 5px;
  }
}
.blog-prev-img {
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;

  height: 215px;
  border: solid 1px lightblue;
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

