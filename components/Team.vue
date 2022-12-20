<template>
  <section class="about-section ">
    <div class="hero" style="">
      <div class="hero-body about-hero">
        <div class="title is-size-4 has-text-centered mb-6">
          <h1 class="has-text-weight-bold has-text-primary">
           TEAM
            <!-- <span></span>
            <b-icon
              style="color: #2BABE2"
              icon="chat-alert-outline"
              size="is-small"
            >
            </b-icon> -->
          </h1>
          <h1 class="has-text-weight-bold  mt-5 has-text-link ">
            <strong>DISCOVER GROWING TALENTS</strong>
          </h1>
        </div>
        <div class="columns mt-6" >
          <div class="column" >
            
             
                <div class="about-img m-auto">
              <b-image
                :src='require("~/assets/images/a.png")'
                alt="Profile"
                ratio="1by1"
                :rounded="rounded"
                id="image"
              ></b-image>
            </div>
              
                <h4
                  class="
                    title
                    is-size-5
                    has-text-weight-bold 
                    has-text-centered
                  "
                  style="margin-bottom:15px"
                >
                 Cedric Houngbedji
                </h4>
              
            
                <h4 class="has-text-primary  has-text-centered has-text-weight-bold" >Dev Mobile </h4>
             
              
             
            
          </div>

          <div class="column" >
            
             
                <div class="about-img m-auto">
              <b-image
                :src='require("~/assets/images/b.jpeg")'
                alt="Profile"
                ratio="1by1"
                :rounded="rounded"
                id="image"
              ></b-image>
            </div>
              
                <h4
                  class="
                    title
                    is-size-5
                    has-text-weight-bold 
                    has-text-centered
                  "
                  style="margin-bottom:15px"
                >
                 Abiodoun Paraiso
                </h4>
              
            
                <h4 class="has-text-primary  has-text-centered has-text-weight-bold" >Dev Fullstack web </h4>
             
              
             
            
          </div>

          <div class="column" >
            
             
                <div class="about-img m-auto" >
              <b-image
                :src='require("~/assets/images/file.jpg")'
                alt="Profile"
                ratio="1by1"
                :rounded="rounded"
                id="image"
              ></b-image>
            </div>
              
                <h4
                  class="
                    title
                    is-size-5
                    has-text-weight-bold 
                    has-text-centered
                  "
                  style="margin-bottom:15px"
                >
                 Jonh Doe
                </h4>
              
            
                <h4 class="has-text-primary  has-text-centered has-text-weight-bold" >Graphics Designer </h4>
             
              
             
            
          </div>

          <div class="column" >
            
             
                <div class="about-img m-auto" >
              <b-image
                :src='require("~/assets/images/d.jpg")'
                alt="Profile"
                ratio="1by1"
                :rounded="rounded"
                id="image"
              ></b-image>
            </div>
              
                <h4
                  class="
                    title
                    is-size-5
                    has-text-weight-bold 
                    has-text-centered
                  "
                  style="margin-bottom:15px"
                >
                 Jane Doe
                </h4>
              
            
                <h4 class="has-text-primary  has-text-centered has-text-weight-bold" >Copy Writter </h4>
             
              
             
            
          </div>
         

        </div>
      </div>
    </div>
  <hr style=" border-top: 1px solid #BB9140;">
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