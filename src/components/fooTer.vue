<template>
  <footer>
    <div class="footer__a-link-container">
      <a href="inicio" class="footer__a-link active">Inicio</a>
      <a href="acerca-de-nosotros" class="footer__a-link">Acerca de nosotros</a>
      <a href="historia" class="footer__a-link">Historia</a>
      <a href="contacto" class="footer__a-link">Contacto</a>
    </div>
    <div class="footer__media-container">
      <a href="">
        <img src="/images/in-icon.png" alt="indeed icon png" class="footer__icon">
      </a>
      <a href="">
        <img src="/images/v-icon.png" alt="v icon png" class="footer__icon">
      </a>
      <a href="">
        <img src="/images/cam-icon.png" alt="instagram icon png" class="footer__icon">
      </a>
      <a href="">
        <img src="/images/twt-icon.png" alt="twitter icon png" class="footer__icon">
      </a>
      <a href="">
        <img src="/images/fb-icon.png" alt="facebook icon png" class="footer__icon">
      </a>
    </div>
  </footer>
</template>
<script>
export default {
  data() {
    return {
    }
  }
}
</script>

<style scoped lang="scss">
footer {
  width: 100%;
  min-height: 203px;
  background-color: var(--main-color);
  padding-block: 58px;
  padding-inline: 78px;
  position: relative;

  &::after {
    content: '';
    position: absolute;
    right: var(--main-grid-padding);
    top: 50%;
    transform: translateY(-50%);
    width: 55px;
    height: 55px;
    background: url(/images/fill-2.png);
    background-size: contain;
    background-repeat: no-repeat;
  }
}

.footer__a-link-container {
  display: flex;
  flex-wrap: wrap;
  gap: 10px 30px;
  margin-bottom: 20px;
}

.footer__a-link {
  color: var(--dark-two);
  letter-spacing: 1.14px;
  font-size: 13px;
  &:hover{
    color: var(--dark-two);
    letter-spacing: normal;
    font-weight: 700;
  }
}

.footer__a-link.active {
  color: var(--dark-two);
  letter-spacing: normal;
  font-weight: 700;
}

.footer__media-container {
  display: flex;
  gap: 12px;
}

.footer__icon {
  width: 31px;
  height: 31px;
}
</style>