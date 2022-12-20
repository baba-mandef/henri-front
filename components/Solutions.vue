<template>
  <div class="hero">
    <div class="hero-body work-hero">
      <div class="column is-3">
        <div class="line"></div>
      </div>
      <div
        class="title is-size-4 has-text-centered"
        style="margin-top: 15px; margin-bottom: 30px"
      >
        <p class="has-text-primary" style="padding-bottom: 20px">
          SOLUTIONS
          <!-- <b-icon
          icon="folder-outline"
          size="#is-small"
          style="color: #2babe2"
        ></b-icon> -->
        </p>
        <h1 class="has-text-weight-bold has-text-link">
          <strong>INNOVATION A PASSION</strong>
        </h1>
    </div>
      <div class="columns">
          <div class="column is-5">
          
              <div style="margin-bottom:15px">
                <img src="~/assets/images/d.png" alt="">
              </div>
              <div>
                <h4
                  class="
                    title
                    is-size-5
                    has-text-weight-bold has-text-left
                   has-text-link
                  "
                  style="margin-bottom:15px"
                >
                  Na Al’heri Food
                </h4>
              </div>
              <div style="margin-bottom:15px">
                <h4 class="has-text-primary has-text-weight-bold" >
                  Na Al’heri Food is a food platform based in Porto-Novo at Benin. 
                  NAF provides some features like food delivery, cooking recieps and a huges restaurant catalog.
                </h4>
              </div>
              <div style="display: flex; justify-content: flex-start">
                <button class="button is-link is-outlined">See Details >></button>
              </div>
            </div>
          
      </div>
       <div class="columns" style="display: flex; justify-content: flex-end">
          <div class="column is-5" >
          
              <div style="margin-bottom:15px">
                <img src="~/assets/images/m.png" alt="">
              </div>
              <div>
                <h4
                  class="
                    title
                    is-size-5
                    has-text-weight-bold has-text-left
                   has-text-link
                  "
                  style="margin-bottom:15px"
                >
                  I want
                </h4>
              </div>
              <div style="margin-bottom:15px">
                <h4 class="has-text-primary has-text-weight-bold" >
                  I want is a african social media based on users whish. 
                  I want is availaible on your browser and all your devices Android, iOS, windows and linux.
                </h4>
              </div>
              <div style="display: flex; justify-content: flex-start">
                <button class="button is-link is-outlined">See Details >></button>
              </div>
            </div>
          
      </div>

       <div class="columns" style="display: flex; justify-content: flex-start">
          <div class="column is-5" >
          
              <div style="margin-bottom:15px">
                <img src="~/assets/images/s.png" alt="">
              </div>
              <div>
                <h4
                  class="
                    title
                    is-size-5
                    has-text-weight-bold has-text-left
                   has-text-link
                  "
                  style="margin-bottom:15px"
                >
                  SchoolMan
                </h4>
              </div>
              <div style="margin-bottom:15px">
                <h4 class="has-text-primary has-text-weight-bold" >
                  SchoolManager is a Desktop application that provides you all the tools you need to manage a School. 
                  It features cover all the school management sides. SchoolMan is available on windows, linux and macOS.
                </h4>
              </div>
              <div style="display: flex; justify-content: flex-start">
                <button class="button is-link is-outlined">See Details >></button>
              </div>
            </div>
          
      </div>

      
      <div style="display: flex; justify-content: flex-end">
      <div class="column is-3">
        <div class="line"></div>
      </div>
      </div>
    </div>
  </div>
</template>

<script>
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
  border: solid 1px #2babe2;
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
.line {
  /*  width: 80%; */
  height: 10px;
  border: none;
  margin-top: 50px;
  border-radius: 10px;
  background-color: #393357;
}
</style>

