<template>
  <div class="hero-body work-hero">
    <div
      class="has-text-centered"
      style="margin-top: 15px; margin-bottom: 30px"
    >
      <p class="title is-size-4 is-size-5-mobile" style="padding-bottom: ">
        Contact
      
      </p>
    </div>
    <div class="columns">
      <div class="column is-half">
        <div class="contact-img"></div>
      </div>

      <div
        class="column"
      >
          <form action="">
             <b-field label="Nom">
            <b-input></b-input>
        </b-field>
         <b-field label="Email">
            <b-input type="email"></b-input>
        </b-field>
        <b-field label="Message">
            <b-input maxlength="200" type="textarea"></b-input>
        </b-field>
          </form>
           <b-button type="is-primary" expanded outlined>
              ENVOYER
          </b-button>
      </div>
    </div>
    
  </div>
</template>



<style>
.contact-img{
  background-repeat: no-repeat;
          padding: 20px;
          background-size:contain;
          background-position:center;
          background-image: url('../assets/images/4.png');
          height:300px;
         margin: 0;
}

@media screen and (min-width: 768px) {

  .contact-img{
    margin-top: 60px;
  }
}

.center {
  margin: 0;

  position: absolute;
  top: 50%;
  left: 50%;
  -ms-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
}

</style>

