<template>
  <div :style="`background-color: ${!confirmed || loading ? '#7EA1C4' : (isFather ? '#46FF66' : '#FF4537') }`" class="main-body">
    <div v-if="!loading && confirmed" class="pyro">
      <div class="before"></div>
      <div class="after"></div>
    </div>
    <transition name="fade" mode="out-in">
      <div v-if="loading" class="loader loader--style8" title="7">
        <svg version="1.1" id="Layer_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
          width="96px" height="120px" viewBox="0 0 24 30" style="enable-background:new 0 0 50 50;" xml:space="preserve">
          <rect x="0" y="10" width="4" height="10" fill="#333" opacity="0.2">
            <animate attributeName="opacity" attributeType="XML" values="0.2; 1; .2" begin="0s" dur="0.6s" repeatCount="indefinite" />
            <animate attributeName="height" attributeType="XML" values="10; 20; 10" begin="0s" dur="0.6s" repeatCount="indefinite" />
            <animate attributeName="y" attributeType="XML" values="10; 5; 10" begin="0s" dur="0.6s" repeatCount="indefinite" />
          </rect>
          <rect x="8" y="10" width="4" height="10" fill="#333"  opacity="0.2">
            <animate attributeName="opacity" attributeType="XML" values="0.2; 1; .2" begin="0.15s" dur="0.6s" repeatCount="indefinite" />
            <animate attributeName="height" attributeType="XML" values="10; 20; 10" begin="0.15s" dur="0.6s" repeatCount="indefinite" />
            <animate attributeName="y" attributeType="XML" values="10; 5; 10" begin="0.15s" dur="0.6s" repeatCount="indefinite" />
          </rect>
          <rect x="16" y="10" width="4" height="10" fill="#333"  opacity="0.2">
            <animate attributeName="opacity" attributeType="XML" values="0.2; 1; .2" begin="0.3s" dur="0.6s" repeatCount="indefinite" />
            <animate attributeName="height" attributeType="XML" values="10; 20; 10" begin="0.3s" dur="0.6s" repeatCount="indefinite" />
            <animate attributeName="y" attributeType="XML" values="10; 5; 10" begin="0.3s" dur="0.6s" repeatCount="indefinite" />
          </rect>
        </svg>
      </div>
      <div v-else class="center">
      
        <div  class="row">
          <p class="main-text">
          🤱🏼
          </p>
          <p style="opacity: 0.5" class="main-text">
          Bruno vai ser pai? 
          </p>
          
        </div>
        <div class="row">
          <p class="main-text" style="color: white" >
            {{ !confirmed ? '50% de chance 🧸' : (isFather ? 'Sim 🥳' : 'Não 🥳') }}
          </p>

        </div>
        <div class="row">
          <p class="secondary-text" >
            🤔🩸 <span style="opacity: 0.5">{{days}} dias sem descer</span> 🩸🤔
          </p>
          
        </div>
      </div>
    </transition>
   
  </div>
</template>
<script>
  export default {
    data() {
      return {
        confirmed: false,
        isFather: false,
        days: 18, 
        loading: true,
      }
    },

    created(){
      let parent = this;
      setTimeout(() => {
        parent.loading = false;
      }, 1500)
    }
  }
</script>
<style lang="scss">
body {
  margin: 0;
}
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
   
 }
 .main-text {
   font-size:8vw;
   font-weight: 900;
   text-align: center;
   margin: 0;
   /* opacity: 0.5; */
   /* color: white; */
   font-family: 'Roboto', sans-serif;
 }
 .secondary-text {
   font-size: 2vw;
   text-align: center;
    /* opacity: 0.5; */
   font-family: 'Roboto', sans-serif;
   font-weight: 100;
 }

 .loader{
  /* margin: auto auto 2em; */
  margin: auto;
  height: 100%;
  width: 100%;
  text-align: center;
  padding: 1em;

  display: inline-block;
  vertical-align: center;
}

/*
  Set the color of the icon
*/
svg path,
svg rect{
  fill: white;
}

.fade-enter-active, .fade-leave-active {
  transition: opacity .5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active em versões anteriores a 2.1.8 */ {
  transition: opacity 2s;
  
}


$particles: 200;
$width: 1000;
$height: 1000;

// Create the explosion...
$box-shadow: ();
$box-shadow2: ();
@for $i from 0 through $particles {
  $box-shadow: $box-shadow,
               random($width)-$width / 2 + px
               random($height)-$height / 1.2 + px
               hsl(random(360), 100, 50);
  $box-shadow2: $box-shadow2, 0 0 #fff
}
@mixin keyframes ($animationName) {
    @-webkit-keyframes #{$animationName} {
        @content;
    }

    @-moz-keyframes #{$animationName} {
        @content;
    }

    @-o-keyframes #{$animationName} {
        @content;
    }

    @-ms-keyframes #{$animationName} {
        @content;
    }

    @keyframes #{$animationName} {
        @content;
    }
}

@mixin animation-delay ($settings) {
    -moz-animation-delay: $settings;
    -webkit-animation-delay: $settings;
    -o-animation-delay: $settings;
    -ms-animation-delay: $settings;
    animation-delay: $settings;
}

@mixin animation-duration ($settings) {
    -moz-animation-duration: $settings;
    -webkit-animation-duration: $settings;
    -o-animation-duration: $settings;
    -ms-animation-duration: $settings;
    animation-duration: $settings;
}

@mixin animation ($settings) {
    -moz-animation: $settings;
    -webkit-animation: $settings;
    -o-animation: $settings;
    -ms-animation: $settings;
    animation: $settings;
}

@mixin transform ($settings) {
    transform: $settings;
    -moz-transform: $settings;
    -webkit-transform: $settings;
    -o-transform: $settings;
    -ms-transform: $settings;
}

body {
  margin:0;
  padding:0;
  background: #000;
  overflow: hidden;
}

.pyro > .before, .pyro > .after {
  position: absolute;
  width: 5px;
  height: 5px;
  border-radius: 50%;
  box-shadow: $box-shadow2;
  @include animation((1s bang ease-out infinite backwards, 1s gravity ease-in infinite backwards, 5s position linear infinite backwards));
}
    
.pyro > .after {
  @include animation-delay((1.25s, 1.25s, 1.25s));
  @include animation-duration((1.25s, 1.25s, 6.25s));
}
        
@include keyframes(bang) {
  to {
    box-shadow:$box-shadow;
  }
}
    
@include keyframes(gravity)  {
  to {
    @include transform(translateY(200px));
    opacity: 0;
  }
}
    
@include keyframes(position) {
  0%, 19.9% {
    margin-top: 10%;
    margin-left: 40%;
  }
  20%, 39.9% {
    margin-top: 40%;
    margin-left: 30%;
  }
  40%, 59.9% {  
    margin-top: 20%;
    margin-left: 70%
  }
  60%, 79.9% {  
    margin-top: 30%;
    margin-left: 20%;
  }
  80%, 99.9% {  
    margin-top: 30%;
    margin-left: 80%;
  }
}

</style>