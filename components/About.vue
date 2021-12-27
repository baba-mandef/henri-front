<template>
  <section class="about-section">
    <div class="hero" style="">
      <div class="hero-body about-hero">
        <div class="title is-size-4 has-text-centered">
          <h1>
            A propos de moi
            <span></span>
            <b-icon
              style="color: #2BABE2"
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
              class="title is-size-4 has-text-centered-mobile is-size-5-mobile"
            >
              Salaou-Deen Henri-Joël A. Paraïso
            </h1>
            <div>
              <p
                style="color: black"
                class="has-text-justified has-text-centered-mobile"
              >
                Hi ! Je suis Sadi Henri Paraïso. Titulaire d'une licence en
                Systèmes Informatiques et Logiciels, je suis développeur web et
                mobile. A mes heures perdues, je joue aux jeux vidéos, je
                partage des memes et j'explore.
              </p>
              <hr />
              <h5 class="is-title has-text-centered-mobile">
                <a href="https://github.com/shadowcompiler">
                  <span style="padding-right: 5px"
                    ><b-icon
                      style="color: black"
                      icon="github"
                      size="is-medium"
                    >
                    </b-icon
                  ></span>
                </a>
                <a href="https://t.me/imsadi">
                  <span style="padding-right: 5px"
                    ><b-icon
                      style="color: black"
                      icon="telegram"
                      size="is-medium"
                    >
                    </b-icon
                  ></span>
                </a>
                <a href="https://twitter.com/shadow_compiler">
                  <span style="padding-right: 5px"
                    ><b-icon
                      style="color: black"
                      icon="twitter"
                      size="is-medium"
                    >
                    </b-icon
                  ></span>
                </a>

                <a href="https://web.facebook.com/0000002sdp">
                  <span style="padding-right: 5px"
                    ><b-icon
                      style="color: black"
                      icon="facebook"
                      size="is-medium"
                    >
                    </b-icon
                  ></span>
                </a>
              </h5>
            </div>
          </div>
          <div class="column is-half about-text">
            <div class="title is-4 is-hidden-mobile has-text-centered">
              <h4>
                Tech Stack
                <b-icon
                  style="color: #2BABE2"
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
                      ><b-icon
                        style="color: #2BABE2"
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
                        style="color: #2BABE2"
                        icon="api"
                        size="is-small"
                      >
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
                        style="color: #2BABE2"
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
                        style="color: #2BABE2"
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
                        style="color: #2BABE2"
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
                        style="color: #2BABE2"
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
                        style="color: #2BABE2"
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
                            style="color: #2BABE2"
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
                            style="color: #2BABE2"
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
</template>

<script>
export default {
  data() {
    return {
      rounded: true,
    };
  },
};
</script>


<style>
.tabs li.is-active a {
  color: #2BABE2;
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
  border-radius: 100px;
  margin-bottom: 10px;
}
@media screen and (max-width: 768px) {
  .about-img {
    margin: auto;
  }
} ;
</style>

