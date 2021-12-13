<template>
  <section class="section">
    <section class="hero">
      <div class="hero-body">
        <div class="container is-max-desktop" v-if="loaded">
          <div v-for="post in posts" :key="post.id">
            <h3 class="title is-3 has-text-centered">
              {{ post.title }}
            </h3>
            <div
              class="has-text-centered"
              style="margin-top: 50px; margin-bottom: 60px"
            >
              <img :src="post.banner" alt="Banner" />
            </div>
            <div class="container has-text-justified">
              <p v-html="post.post"></p>
            </div>

            <hr />
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
              {{ post.view }}
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

        <div class="container is-max-desktop" v-if="loaded">
          <h3 class="title is-3" style="padding-bottom:30px">Commentaires</h3>

         <div>
            <div class="columns" v-for="comment in comments" :key="comment.id">
            <div class="column is-full comment">
              <div class="media">
                <div class="media-left">
                  <figure class="image is-48x48">
                    <img
                      :src="comment.author_pic"
                      alt="Author picture"
                    />
                  </figure>
                </div>
                <div class="media-content">
                 
                  <p>{{comment.body}}</p>
                  <hr>
                   <p class="title is-6 has-text-right">{{comment.author_name}}, {{comment.created_at | humanizeDate}}</p>
                </div>
              </div>
            </div>
          </div>

   

         </div>
        </div>



      </div>
    </section>
  </section>
</template>

<script>
import axios from "axios";

export default {
  layout: "blog",

  data() {
    return {
      posts: [],
      pk: null,
      comments: [],
      loaded: false,
      ip: null,
    };
  },

  filters: {
    humanizeDate(value) {
      var moment = require("moment");
      moment().format();

      return moment(value).fromNow();
    },
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
    var url =
      "http://sadih.herokuapp.com/api/v1/blog/post?slug=" +
      this.$route.query.slug;

    axios
      .get(url)
      .then((response) => {
        this.posts = response.data;
        var post_pk = response.data[0]["id"];
        this.pk = post_pk;

        axios
          .get("http://sadih.herokuapp.com/api/v1/blog/comment?post=" + post_pk)
          .then((response) => {
            this.comments = response.data;

            this.loaded = true;
            axios
            .get("http://sadih.herokuapp.com/api/v1/countView/?post=" + post_pk)
            .then(function response(){
              console.log(response.data);

            }
            .catch(function error(){
              console.log(error)
            }))
          })
          .catch((error) => {
            this.snackbar();
            console.log(error);
          });
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
  background-color: rgb(221, 219, 219);
  border-radius: 10px;
}
</style>
