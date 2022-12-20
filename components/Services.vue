<template>
  <section class="about-section container">
    <div class="hero" style="">
      <div class="hero-body about-hero">
        <div class="title is-size-4 has-text-centered">
          <h1 class="has-text-weight-bold has-text-primary">
            WHAT WE DO ?
            <!-- <span></span>
            <b-icon
              style="color: #2BABE2"
              icon="chat-alert-outline"
              size="is-small"
            >
            </b-icon> -->
          </h1>
          <h1 class="has-text-weight-bold  mt-5 has-text-link ">
            <strong>FEEL FREE TO DISCOVER OUR SERVICES</strong>
          </h1>
        </div>
        <div class="columns">
          <div class="column">
            <div class="box">
              <div class="konsole-icon" style="margin-bottom:15px"></div>
              <div>
                <h4
                  class="
                    title
                    is-size-5
                    has-text-weight-bold has-text-left
                   
                  "
                  style="margin-bottom:15px"
                >
                  Development
                </h4>
              </div>
              <div style="margin-bottom:15px">
                <h4 class="has-text-primary has-text-weight-bold" >Scalable web and apps implementation.</h4>
              </div>
              <div style="display: flex; justify-content: flex-start">
                <button class="button is-link is-outlined">See Details >></button>
              </div>
            </div>
          </div>
          <div class="column"> 
             <div class="box">
              <div class="paint-icon" style="margin-bottom:15px"></div>
              <div>
                <h4
                  class="
                    title
                    is-size-5
                    has-text-weight-bold has-text-left
                   
                  "
                  style="margin-bottom:15px"
                >
                  Design
                </h4>
              </div>
              <div style="margin-bottom:15px">
                <h4  class="has-text-primary has-text-weight-bold">User Interface and User Experience.</h4>
              </div>
              <div style="display: flex; justify-content: flex-start">
                <button class="button is-link is-outlined">See Details >></button>
              </div>
            </div>
          </div>
          <div class="column">
             <div class="box">
              <div class="file-icon" style="margin-bottom:15px"></div>
              <div>
                <h4
                  class="
                    title
                    is-size-5
                    has-text-weight-bold has-text-left
                   
                  "
                  style="margin-bottom:15px"
                >
                  Content Production
                </h4>
              </div>
              <div style="margin-bottom:15px">
                <h4  class="has-text-primary has-text-weight-bold">Written, audio and visual content.</h4>
              </div>
              <div style="display: flex; justify-content: flex-start">
                <button class="button is-link is-outlined">See Details >></button>
              </div>
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
  color: #393357;
}
.konsole-icon {
  height: 100px;
  width: 100px;
  background-image: url("~/assets/images/konsole.png");
}
.paint-icon {
  height: 100px;
  width: 100px;
  background-image: url("~/assets/images/palette.png");
}
.file-icon {
  height: 100px;
  width: 100px;
  background-image: url("~/assets/images/file.png");
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
.secolor{
  color: #BB9140
}
</style>