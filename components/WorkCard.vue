<template>
  <div class="hero-body work-hero" v-if="loaded">
    <div
      class="has-text-centered"
      style="margin-top: 15px; margin-bottom: 30px"
    >
      <p class="title is-size-4 is-size-5-mobile" style="padding-bottom: ">
        Projets récents
        <b-icon
          icon="folder-outline"
          size="#is-small"
          style="color: lightblue"
        ></b-icon>
      </p>
    </div>
    <div class="columns">
      <div class="column is-half">
        <div class="work-img"></div>
      </div>

      <div
        class="column is-3 is work-prev"
        v-for="work in works"
        :key="work.id"
      >
        <div
          class="work-prev-img"
          v-bind:style="{
            'background-image': 'url(' + work.banner + ')',
          }"
        ></div>
        <hr />
        <div class="">
          <small class="is-uppercase"
            >{{ new Date(work.created_at) | dateFormat("DD MMM YYYY") }}
            <span
              ><b-icon style="color: lightblue" icon="calendar" size="is-small">
              </b-icon>
            </span>
          </small>
        </div>
        <hr />
        <div>
          <p class="subtitle is-size-6 is-uppercase">
            {{ work.name }}
          </p>
          <div class="buttons">
            <b-button type="is-primary" expanded outlined
              ><nuxt-link
                :to="{
                  path: 'work/work',
                  query: { slug: '' + work.slug + '' },
                }"
                ><span style="color: black">Voir plus</span></nuxt-link
              ></b-button
            >
          </div>
        </div>
      </div>
    </div>
    <div class="column is-full has-text-centered">
      <p class="title is-size-5">
        <nuxt-link to="/work" style="color: lightblue"
          >Voir tous les projets
          <span
            ><b-icon
              style="color: lightblue"
              icon="hand-pointing-left"
            ></b-icon></span
        ></nuxt-link>
      </p>
    </div>
  </div>
</template>


<script>
import axios from "axios";
export default {
  data() {
    return {
      loaded: false,
      works: [],
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
      .get("http://192.168.0.193:8000/api/v1/work")
      .then((response) => {
        const data = response.data;
        this.works = this.getLatest(2, data);
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
.work-img{
  background-repeat: no-repeat;
          padding: 20px;
          background-size:contain;
          background-position:center;
          background-image: url('../assets/images/3.png');
          height:300px;
         margin: 0;
}
.work-prev {
  /*  border: solid 1px lightblue; */
  border-radius: 2%;
  margin: 5px;
}
@media screen and (min-width: 768px) {
  .work-prev {
    /*  border: solid 1px lightblue; */
    border-radius: 2%;
    margin: 5px;
  }
  .work-img{
    margin-top: 60px;
  }
}
.work-prev-img {
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

.work-prev {
  margin: 15px;
}
</style>

