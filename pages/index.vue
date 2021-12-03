<template>
  <section class="section">
    <section class="about-section">
      <div class="hero " style="">
        <div class="hero-body about-hero">
          <div class="title is-size-4 has-text-centered">
            <h1>
              A propos de moi
              <span></span>
              <b-icon
                style="color: lightblue"
                icon="chat-alert-outline"
                size="is-small"
              >
              </b-icon>
            </h1>
          </div>
          <div class="columns">
            <div class="column is-half about-text">
              <div
                class="
                  title
                  is-4
                  has-text-left
                  is-hidden-mobile
                  has-text-centered-mobile
                "
              >
                <h4>Qui suis-je ?</h4>
              </div>
              <div class="about-img">
                <b-image
                  :src="require('~/assets/images/2.png')"
                  alt="Profile"
                  ratio="1by1"
                  :rounded="rounded"
                  id="image"
                ></b-image>
              </div>
              <h1
                class="
                  title
                  is-size-4
                  has-text-centered-mobile
                  is-size-5-mobile
                "
              >
                Salaou-Deen Henri-Joël A. Paraïso
              </h1>
              <div>
                <p
                  style="color: black"
                  class="has-text-justified has-text-centered-mobile"
                >
                  Hi ! Je suis Sadi Henri Paraïso. Titulaire d'une licence en
                  Systèmes Informatiques et Logiciels, je suis développeur web
                  et mobile. A mes heures perdues, je joue aux jeux vidéos, je
                  partage des memes et j'explore.
                </p>
              </div>
            </div>
            <div class="column is-half about-text">
              <div class="title is-4 is-hidden-mobile has-text-centered">
                <h4>
                  Tech Stack
                  <b-icon
                    style="color: lightblue"
                    icon="cog-outline"
                    size="is-small"
                  >
                  </b-icon>
                </h4>
              </div>

              <div class="columns is-hidden-mobile">
                <Card title="Python" icon="language-python">
                  <ul class="has-text-left">
                    <li>
                      Django
                      <span
                        ><b-icon style="color: lightblue" icon="web" size="is-small">
                        </b-icon
                      ></span>
                    </li>
                    <li>
                      DRF
                      <span
                        ><b-icon style="color: lightblue" icon="api" size="is-small">
                        </b-icon
                      ></span>
                    </li>
                  </ul>
                </Card>
                <Card title="JavaScript" icon="language-javascript">
                  <ul class="has-text-left">
                    <li>
                      Vuejs
                      <span
                        ><b-icon
                          style="color: lightblue"
                          icon="vuejs"
                          size="is-small"
                        >
                        </b-icon
                      ></span>
                    </li>
                    <li>
                      Nuxtjs
                      <span
                        ><b-icon
                          style="color: lightblue"
                          icon="nuxt"
                          size="is-small"
                        >
                        </b-icon
                      ></span>
                    </li>
                  </ul>
                </Card>
              </div>
              <div class="columns is-hidden-mobile">
                <Card title="Kotlin" icon="language-kotlin">
                  <ul class="has-text-left">
                    <li>
                      Android
                      <span
                        ><b-icon
                          style="color: lightblue"
                          icon="android"
                          size="is-small"
                        >
                        </b-icon
                      ></span>
                    </li>
                    <br />
                    <!--   <li>
                      Nuxtjs
                      <span
                        ><b-icon
                          style="color: gray"
                          icon="nuxt"
                          size="is-small"
                        >
                        </b-icon
                      ></span>
                    </li> -->
                  </ul>
                </Card>
                <Card title="Databases" icon="database">
                  <ul class="has-text-left">
                    <li>
                      MySql
                      <span
                        ><b-icon
                          style="color: lightblue"
                          icon="database-outline"
                          size="is-small"
                        >
                        </b-icon
                      ></span>
                    </li>
                    <li>
                      Postgresql
                      <span
                        ><b-icon
                          style="color: lightblue"
                          icon="database-outline"
                          size="is-small"
                        >
                        </b-icon
                      ></span>
                    </li>
                  </ul>
                </Card>
              </div>
              <div
                class="
                  columns
                  is-hidden-fullhd is-hidden-desktop is-hidden-tablet
                "
              >
                <CardB>
                  <template v-slot:header>
                    <div
                      class="title is-5 has-text-centered"
                      style="margin: auto"
                    >
                      <h4>
                        Tech Stack
                        <b-icon
                          style="color: gray"
                          icon="cog-outline"
                          size="is-small"
                        >
                        </b-icon>
                      </h4>
                    </div>
                  </template>

                  <b-tabs type="is-boxed">
                    <b-tab-item label="" icon="language-python">
                      <ul class="has-text-left">
                        <li>
                          Django
                          <span
                            ><b-icon
                              style="color: lightblue"
                              icon="web"
                              size="is-small"
                            >
                            </b-icon
                          ></span>
                        </li>
                        <li>
                          DRF
                          <span
                            ><b-icon
                              style="color: lightblue"
                              icon="api"
                              size="is-small"
                            >
                            </b-icon
                          ></span>
                        </li>
                      </ul>
                    </b-tab-item>
                    <b-tab-item label="" icon="language-javascript">
                      <ul class="has-text-left">
                        <li>
                          Vuejs
                          <span
                            ><b-icon
                              style="color: 161d30"
                              icon="vuejs"
                              size="is-small"
                            >
                            </b-icon
                          ></span>
                        </li>
                        <li>
                          Nuxtjs
                          <span
                            ><b-icon
                              style="color: 161d30"
                              icon="nuxt"
                              size="is-small"
                            >
                            </b-icon
                          ></span>
                        </li>
                      </ul>
                    </b-tab-item>

                    <b-tab-item label="" icon="language-kotlin">
                      <ul class="has-text-left">
                        <li>
                          Android
                          <span
                            ><b-icon
                              style="color: 161d30"
                              icon="android"
                              size="is-small"
                            >
                            </b-icon
                          ></span>
                        </li>
                      </ul>
                    </b-tab-item>

                    <b-tab-item label="" icon="database">
                      <ul class="has-text-left">
                        <li>
                          MySql
                          <span
                            ><b-icon
                              style="color: 161d30"
                              icon="database-outline"
                              size="is-small"
                            >
                            </b-icon
                          ></span>
                        </li>
                        <li>
                          Postgresql
                          <span
                            ><b-icon
                              style="color: 161d30"
                              icon="database-outline"
                              size="is-small"
                            >
                            </b-icon
                          ></span>
                        </li>
                      </ul>
                    </b-tab-item>
                  </b-tabs>
                </CardB>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section class="blog-section">
      <div class="hero">
        <div class="hero-body blog-hero">
          <div
            class="has-text-centered"
            style="margin-top: 15px; margin-bottom: 30px"
          >
            <p class="title is-size-4 is-size-5-mobile" style="padding-bottom:">Articles récents <b-icon icon="file-document-outline" size="#is-small" style='color:lightblue'></b-icon></p>
          </div>
           <div class="columns" v-if="loaded">
             <div
              class="column is blog-prev"
              v-for="post in posts"
              :key="post.id"
            >
              <div
                class="blog-prev-img"
                v-bind:style="{'background-image': 'url('+post.banner+')'}"
              ></div>
              <hr>
              <div class="">
                <small class="is-uppercase"
                  >{{ new Date(post.created_at) | dateFormat('DD MMM YYYY')}} |
                  <span
                    ><b-icon style="color: lightblue" icon="folder" size="is-small">
                    </b-icon>
                  </span>
                  {{post.category}} |
                  <span
                    ><b-icon style="color: lightblue" icon="eye" size="is-small">
                    </b-icon>
                  </span>
                  {{post.view}}</small
                >
              </div>
             <hr>
              <div>
                <p class="subtitle is-size-6 is-uppercase ">
                  {{post.title}}
                </p>
                <div class="buttons">
                  <b-button type="is-primary" expanded outlined><nuxt-link :to="{ path: 'blog/post', query: { slug: ''+post.slug+'' }}"><span style="color:black">Lire</span></nuxt-link></b-button>
                </div>
              </div>
            </div>
          </div>
          <div class="column is-full has-text-centered">
            <p class="title is-size-5">
              <nuxt-link to="/blog" style="color: lightblue">Voir tous les articles <span><b-icon style="color:lightblue" icon=""></b-icon></span></nuxt-link>
            </p>
          </div>
        </div>
      </div>
    </section>
  </section>
</template>


<script>
import axios from "axios";
import Card from "~/components/Card.vue";
import CardB from "~/components/CardB.vue";
export default {
  components: { Card, CardB },
  name: "Home",
  data() {
    return {
      rounded: false,
      loaded: false,
      posts: [],
      
    };
  },
  
  created() {
    axios
      .get('http://192.168.0.193:8000/api/v1/blog/post')
      .then(response => {
        const data = response.data;
        for(var i=0; i<3; i++)
        {
          if(data[i] == undefined)
          {
            break
          }

          else{
            this.posts.push(data[i]);
          }
        }
        this.loaded = true;
      }
      );
  },

  layout: "index",
};
</script>

<style>
.tabs li.is-active a{
  color: lightblue;
}
.blog-prev{
/*  border: solid 1px lightblue; */
border-radius: 2%;
 margin:5px;
 
}
@media screen and (min-width: 768px) {
  .blog-prev{
/*  border: solid 1px lightblue; */
border-radius: 2%;
 margin:5px;
 
}

  
} ;
.blog-prev-img {

  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  
  height: 215px;
  border: solid 1px lightblue;

}

.hero-img {
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
}
.hero1 {
  height: 590px;
}
.center {
  margin: 0;

  position: absolute;
  top: 50%;
  left: 50%;
  -ms-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
}
.about-text {
  padding: 30px;
}
.about-img {
  width: 150px;
}

.b-image-wrapper {
  border: solid 2px;
  border-radius: 4%;
  margin-bottom: 10px;
}
@media screen and (max-width: 768px) {
  .about-img {
    margin: auto;
  }

  .blog-prev{

 margin: 15px;
}
  
} ;
</style>
