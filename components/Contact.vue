<template>
  <div class="hero-body work-hero">
    <div class="title is-size-4 has-text-centered mb-6">
          <h1 class="has-text-weight-bold has-text-primary">
           CONTACT US
            <!-- <span></span>
            <b-icon
              style="color: #2BABE2"
              icon="chat-alert-outline"
              size="is-small"
            >
            </b-icon> -->
          </h1>
          <h1 class="has-text-weight-bold  mt-5 has-text-link ">
            <strong>WE’D LOVE TO HEAR FROM YOU !</strong>
          </h1>
        </div>
    <div class="columns">
      <div class="column is-half m-auto">
        
        <form action="">
          <b-field label="Nom"
          type="is-link"
          >
            
            <b-input></b-input>
          </b-field>
          <b-field label="Email" type="is-link">
            <b-input type="email"></b-input>
          </b-field>
          <b-field label="Message" type="is-link">
            <b-input maxlength="200" type="textarea"></b-input>
          </b-field>
        </form>
        <b-button type="is-primary" expanded outlined> ENVOYER </b-button>
      </div>
    </div>
     <hr style=" border-top: 1px solid #BB9140;">
  </div>
</template>



<style>



.center {
  margin: 0;

  position: absolute;
  top: 50%;
  left: 50%;
  -ms-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
}
</style>

