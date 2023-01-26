<template>
  <nav class="navbar__container" :class="navbarOpen ? 'navbar__left--closed' :'navbar__left--open'">
    <div class="navbar main-container">
      <div class="navbar__left">
        <div class="navbar__a-container" v-for="(navbarItem, index) in navbarItems" :key=index>
          <a class="navbar__a" :href="navbarItem.anchorName">{{ navbarItem.itemName }}</a>
        </div>
      </div>
      <div class="navbar__right">
        <div class="navbar__lang">
          <span class="navbar__span active">Es</span>
          <span class="navbar__span">En</span>
        </div>
        <div class="button-menu__container">
          <button class="button-menu" @click="toggleNavMenu()">
            <div>I</div>
            <div>I</div>
            <div>I</div>
          </button>
        </div>
      </div>
    </div>
  </nav>

</template>
<script>
export default {
  data() {
    return {
      navbarOpen: false,
      navbarItems: [
        { itemName: 'Inicio', anchorName: 'inicio' },
        { itemName: 'Acerca de nosotros', anchorName: 'acerca-de-nosotros' },
        { itemName: 'Historia', anchorName: 'historia' },
        { itemName: 'Contacto', anchorName: 'contacto' }
      ]
    }
  },
  methods: {
    toggleNavMenu() {
      this.navbarOpen = !this.navbarOpen;
    },
    navbarMobile() {
      this.navbarOpen = (window.innerWidth <= 991) ? true : false;
    }
  },
  beforeMount(){
    this.navbarMobile();
		window.addEventListener('resize', this.navbarMobile);
	}
}
</script>

<style scoped lang="scss">
/*No me parecen tan mal selectores tan largos en este caso por que en
las animaciones hay elementos que tienen que esuchar a .navbar__container*/
.navbar__container {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 110px;
  overflow: hidden;
  z-index: 1;

  .navbar {
    --size-navbar-y: 44px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-block: calc((var(--size-navbar-y)/3) * 2); /*Cálculo para colocar solamente una parte de la altura que aparece en zeppelin como padding*/
    .navbar__left,
    .navbar__right {
      display: flex;
      flex-direction: row;
      color: var(--white);

      .navbar__lang {
        display: flex;
        gap: 15px;
        @media screen and (max-width: 991px) {
          display: none;
        }
        .navbar__span {
          font-size: 13px;
          cursor: pointer;
          text-transform: uppercase;

          &.active {
            font-weight: 700;
          }

          &:hover {
            font-weight: 700;
          }
        }
      }
      .button-menu__container {
        @media screen and (min-width: 991.5px) {
          display: none;
        }
      }

    }
    .navbar__left {
      gap: 10px 35px;
      height: auto;
      flex-direction: row;
      width: min-content;
      position: relative;
      @media screen and (max-width: 991px) {
        flex-direction: column;
        width: 100%;
        overflow: hidden;
        margin-top: calc(var(--size-navbar-y)); 
      }
      .navbar__a-container {
        .navbar__a {
          font-size: 16px;
          padding-block: calc(var(--size-navbar-y)/3); /*Complemento del cálculo */
          padding-inline-start: 4px;
          position: relative;
          letter-spacing: 0.04em;
          white-space: nowrap;

          &::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 1px;
            width: 0;
            height: 2px;
            background-color: var(--white);
          }

          &:hover {
            font-weight: 700;
            letter-spacing: 0.001em;

            &::after {
              animation: navbarAHover .5s;
              width: 100%;
            }
          }
        }
      }
    }
  }

  @media screen and (max-width:991px){
    &.navbar__left--open {
      height: 100%;
      background-color: #0119;
      .navbar {
        align-items: start;
        .navbar__left {
          height: auto;
        }
        .navbar__right {
          .button-menu__container {
            .button-menu {
              div {
                &:nth-child(1) {
                  transform: translate(50%, 0%) rotateZ(45deg);
                }
                &:nth-child(2) {
                  display: none;
                }
                &:nth-child(3) {
                  transform: translate(-50%, 0%) rotateZ(-45deg);
                }
              }
            }
          }
        }
      }
    }  
    &.navbar__left--closed {
      .navbar {
        align-items: start;
        .navbar__left {
          height: 0;
        }
        .navbar__right {
          .button-menu__container {
            .button-menu {
              div {
                transform: translate(-50%, 0%);
              }
            }
          }
        }
      }
    }
  }
}
/*Animacion hover en los navbar__a*/

@keyframes navbarAHover {
  0% {
    width: 0px;
  }

  100% {
    width: 100%;
  }
}
</style>