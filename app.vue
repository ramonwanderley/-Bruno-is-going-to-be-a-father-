<template>
  <div :style="`background-color: ${!confirmed || loading ? '#7EA1C4' : (isFather ? '#46FF66' : '#FF4537') }`" class="main-body">
    <div v-if="!loading && confirmed" class="pyro">
      <div class="before"></div>
      <div class="after"></div>
    </div>
    
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
   
  </div>
</template>
<script>
  export default {
    data() {
      return {
        confirmed: true,
        isFather: true,
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
