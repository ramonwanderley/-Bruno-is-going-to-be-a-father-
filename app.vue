<template>
  <div :style="`background-color: ${!confirmed ? 'grey' : (isFather ? 'green' : 'red') }`" class="main-body">
    <div class="center">
    
      <div  class="row">
        <p class="main-text">
        Bruno vai ser pai?
        </p>
      </div>
      <div class="row">
        <p class="main-text" >
          {{ !confirmed ? '50% de chance' : (isFather ? 'Sim' : 'Não') }}
        </p>

      </div>
       <div class="row">
        <p class="secondary-text" >
          {{days}} dias sem descer
        </p>
        
      </div>
    </div>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        confirmed: false,
        isFather: false,
        days: 18, 
      }
    }
  }
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100;0,500;0,900;1,900&display=swap');
  .main-body {
    height: 100%;
    min-height: calc(100vh - 16px);
    width: 100%;
    display: flex;
  }
 .center {
   margin: auto;
 }

 .row {
    margin: auto;
 }
 .main-text {
   font-size:8vw;
   font-weight: 900;
   text-align: center;
   /* color: white; */
   font-family: 'Roboto', sans-serif;
 }
 .secondary-text {
   font-size: 4vw;
  text-align: center;
   
   font-family: 'Roboto', sans-serif;
   font-weight: 100;
 }
</style>