<template>
  <div class="center">
   

    
    <div class="row">
      <p>
      Bruno vai ser pai?<br/>
      </p>
    </div>
    <div class="row">
      <p >
        {{ !confirmed ? '50% de chance' : (isFather ? 'Sim' : 'Não') }}
        
      </p>
    </div>
    
    
  </div>
</template>
<script>
export default {
  data() {
    return {
      confirmed: false,
      isFather: false, 
    }
  }
}
</script>
<style>
 .center {
   display: flex;
   justify-content: center;
   align-items: center;
   flex-wrap: nowrap;

 }

 .row {
  width: 100vw;
  flex-grow: 12;

 }
 .main-text {
   color: brown;
 }
</style>