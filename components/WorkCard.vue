<template>
  <div class="hero-body work-hero">
    <div
      class="has-text-centered"
      style="margin-top: 15px; margin-bottom: 30px"
    >
      <p class="title is-size-4 is-size-5-mobile" style="padding-bottom: ">
        Projets récents
        <b-icon
          icon="folder-outline"
          size="#is-small"
          style="color: #2BABE2"
        ></b-icon>
      </p>
    </div>
     <div v-if="!loaded" class="column is-3">
        <p>
          <b-skeleton height="215px" style=""></b-skeleton>

          <b-skeleton active :count="1"></b-skeleton>
          <b-skeleton height="80px" style=""></b-skeleton>
        </p>
      </div>
    <div class="columns" v-if="loaded">
      <div class="column is-6">
        <div class="work-img"></div>
      </div>

        <div
          class="column  work-prev"
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
                ><b-icon
                  style="color: #2BABE2"
                  icon="calendar"
                  size="is-small"
                >
                </b-icon>
              </span>
            </small>
          </div>
          <hr />
          <div>
            <p class="subtitle is-size-6 is-uppercase">
              {{ work.name }}
            </p>
            <nuxt-link
              :to="{
                path: 'work/single',
                query: { slug: '' + work.slug + '' },
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
    <div class="column is-full has-text-centered">
      <p class="title is-size-5">
        <nuxt-link to="/work" style="color: #2BABE2"
          >Voir tous les projets
          <span
            ><b-icon
              style="color: #2BABE2"
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
      .get(this.$axios.defaults.baseURL+"/api/v1/work")
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
.work-img {
  background-repeat: no-repeat;
  padding: 20px;
  background-size: contain;
  background-position: center;
  background-image: url("../assets/images/3.png");
  height: 300px;
  margin: 0;
}

@media screen and (min-width: 768px) {
  .work-prev {
    /*  border: solid 1px #2BABE2; */
    border-radius: 2%;
    margin: 5px;
  }
  .work-img {
    margin-top: 60px;
  }
}
.work-prev-img {
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

.work-prev {
  margin: 15px;
}
</style>

