<template>
  <section class="main-banner__container">
    <div> <!--Un div extra para un ::after en el lugar correcto-->
      <div class="main-container">
        <div class="main-banner__contenido">
          <h1 class="main-banner__h1">Las mejores raquetas para jugar 
            <span class="main-banner__span">Tennis</span>
          </h1>
          <button class="main-button">
            Acerca de nosotros
          </button>
        </div>
      </div>
    </div>
    

  </section>
</template>
<script>
export default {
  
}
</script>
<style scoped lang="scss">

.main-banner__container {
  background-image: url(/images/group.jpg);
  background-repeat: no-repeat;
  background-size: cover;
  min-height: min-content;
  height: clamp( 600px, 55vw, 785px);
  --tennis-ball-size: 37px;
  >div {
    height: 100%;
    position: relative;
    &::after, &::before {
      content: '';
      position: absolute;
    }
    &::after {
      background-image: url(/images/fill-2.png);
      background-repeat: no-repeat;
      background-size: cover;
      top: clamp(0px, 1vw, 10px);
      left: var(--tennis-ball-size);
      width: var(--tennis-ball-size);
      height: var(--tennis-ball-size);
      z-index: 1;
      @media screen and (max-width:991px) {
        top: 24px;
        left: var(--tennis-ball-size);
        width: var(--tennis-ball-size);
        height: var(--tennis-ball-size);
      }
    }
    &::before {
      background-color: white;
      top: 0;
      left: calc(var(--tennis-ball-size) * 3);
      height: 100%;
      width: 2px;
      @media screen and (max-width:991px) {
        content: none;
      }
    }
    >div.main-container {
      height: 100%;
    }
  }
}
.main-banner__contenido {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: start;
  height: 100%;
  width: clamp(280px, 45vw, 709px);
  .main-banner__h1 {
    font-size: 53px;
    line-height: 68px;
    letter-spacing: -0.05px;
    color: var(--white);
    margin-bottom: 40px;
    overflow-wrap: break-word;      /*Maximo*/
    display: -webkit-box;           /*cinco*/
    -webkit-line-clamp: 5;          /*lineas*/
    -webkit-box-orient: vertical;   /*de*/
    overflow: hidden;               /*texto*/
    text-overflow: ellipsis;        /*posible*/
    .main-banner__span {
      color: var(--main-color);
      font-weight: 800;
    }
  }
}

</style>