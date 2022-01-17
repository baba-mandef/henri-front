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
                ><b-icon style="color: #2babe2" icon="calendar" size="is-small">
                </b-icon>
              </span>
              {{ new Date(post.created_at) | dateFormat("DD MMM YYYY") }} |
              <span
                ><b-icon style="color: #2babe2" icon="folder" size="is-small">
                </b-icon>
              </span>
              {{ post.category }} |
              <span
                ><b-icon style="color: #2babe2" icon="eye" size="is-small">
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
          <h3 class="title is-3" style="padding-bottom: 30px">
            Commentaires
            <b-button
              label="Ajouter un commentaire"
              type="is-primary"
              @click="modal = true"
            />
          </h3>

          <b-collapse :open="modal">
            <div style="padding-bottom: 40px">
              <form action="">
                <b-field label="Votre nom">
                  <b-input
                    v-model="nom"
                    required
                    validation-message="Ce champs est requis"
                  >
                  </b-input>
                </b-field>

                <b-field label="Email (anonyme)">
                  <b-input
                    v-model="email"
                    required
                    validation-message="Ce champs est requis"
                  >
                  </b-input>
                </b-field>

                <b-field label="Commentaire">
                  <b-input
                    v-model="message"
                    type="textarea"
                    required
                    validation-message="Ce champs est requis"
                  >
                  </b-input>
                </b-field>

                <b-field class="file">
                  <b-upload v-model="image" expanded>
                    <a class="button is-primary is-fullwidth">
                      <b-icon icon="upload"></b-icon>
                      <span>{{ "Cliquez pour uploader une image" }}</span>
                    </a>
                  </b-upload>
                </b-field>
                <b-button
                  label="Envoyer"
                  type="is-primary"
                  @click="submit_comment"
                />

                <b-button
                  label="Fermer"
                  type="is-primary"
                  @click="modal = false"
                />
              </form>
            </div>
          </b-collapse>

          <div>
            <div class="columns" v-for="comment in comments" :key="comment.id">
              <div class="column is-full comment">
                <div class="media">
                  <div class="media-left">
                    <figure class="image is-48x48">
                      <img :src="comment.author_pic" alt="Author picture" />
                    </figure>
                  </div>
                  <div class="media-content">
                    <p>{{ comment.body }}</p>
                    <hr />
                    <p class="title is-6 has-text-right">
                      {{ comment.author_name }},
                      {{ comment.created_at | humanizeDate }} à {{new Date(comment.created_at ) | dateFormat("HH : mm")}}
                    </p>
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
      modal: false,
      nom: "",
      email: "",
      message: "",
      image: null,
    };
  },

  filters: {
    humanizeDate(value) {
      var moment = require("moment");
      moment.locale("fr");
      moment().format();

      return moment(value).fromNow();
    },
  },

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

    submit_comment() {
      var FormData = require("form-data");
      // var fs = require("fs-extra");
      var data = new FormData();
      data.append("author_name", this.nom);
      data.append("author_mail", this.email);
      data.append("body", this.message);
      data.append("post", this.pk);
      if (this.image != null) {
        data.append("author_pic", this.image);
      }

      var config = {
        method: "post",
        url: this.$axios.defaults.baseURL + "/api/v1/blog/comment",
        headers: {
          "Content-Type": "multipart/form-data",
        },
        data: data,
      };

      axios(config)
        .then(function (response) {
          // this.modal = false;

          this.$buefy.toast.open("Votre commentaire à été publié avec succès");

          console.log(JSON.stringify(response.data));
          
        })

        .catch(function (error) {
          console.log(error);
        });
    },
  },
  created() {
    var url =
      this.$axios.defaults.baseURL +
      "/api/v1/blog/post?slug=" +
      this.$route.query.slug;

    axios
      .get(url)
      .then((response) => {
        this.posts = response.data;
        var post_pk = response.data[0]["id"];
        this.pk = post_pk;

        axios
          .get(
            this.$axios.defaults.baseURL +
              "/api/v1/blog/comment?post=" +
              post_pk
          )
          .then((response) => {
            this.comments = response.data;

            this.loaded = true;
            axios
              .get(
                this.$axios.defaults.baseURL +
                  "/api/v1/countView/?post=" +
                  post_pk
              )
              .then(
                function response() {
                  console.log(response.data);
                }.catch(function error() {
                  console.log(error);
                })
              );
          })
          .catch((error) => {
            
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
  background-color: rgb(230, 230, 230);
  border-radius: 10px;
}
</style>
