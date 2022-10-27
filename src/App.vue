
<script>
import PageData from './components/PageData.vue';
  export default{
    components:{
    PageData
}
  }
</script>
<template>
  <img class="logo" src="./assets/images/logo.svg" alt="Logo">
  <div class="wraper">
    <div class="comp1">
      <PageData></PageData>
    </div>
    <img class="hero" src="./assets/images/hero-desktop.jpg" alt="Hero">
  </div>
</template>

<style>
  .logo{
    display: none;
  }
  .wraper{
    display: flex;
    justify-content: space-between;
    height: 100%;
  }
  .comp1{
    background-image: url(./assets/images/bg-pattern-desktop.svg);
    background-repeat: no-repeat;
    background-size: cover;
    padding: 4rem;
    padding-left: 8rem;
    padding-right: 15rem;
    width: 60%;
    display: flex;
    flex-direction: column;
  }
  .hero{
    width: 42%;
    height: 100vh;
    object-fit: cover;
    object-position: center;
  }
  @media (max-width: 1300px){
    .comp1{
      justify-content: center;
      padding: 4rem clamp(1rem, 5vw, 8rem) 4rem clamp(1rem, 8vw, 15rem);
      width: 50%;
    }
    .hero{
      width: 50%;
    }
  }
  
  @media (max-width: 850px){
    .wraper{
      flex-direction: column;
    }
    .comp1{
      width: unset;
      padding: 2rem max(4rem, 15%);

    }

    .hero{
      width: min(500px, 100%);
      margin: auto;
      order: -1;
      border-radius: 10px;
      height: unset;
    }
    .logo{
      display: block;
      margin: 30px 20px;
      height: clamp( 20px, 8vw, 60px );
      
    }
  }

  @media (max-width: 500px) {
    .hero{
      border-radius: 0;
    }
  }
  
</style>