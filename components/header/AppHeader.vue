<template>
  <header>
    <div class="cart" :class="openCart ? 'opened' : ''">
      <div class="head">
        <i class="fa-regular fa-xmark" @click="openCart = false"></i>
        <button
          @click="goToCheckout"
          :disabled="$store.state.cartItems.length <= 0"
        >
          <i class="fa-regular fa-badge-check"></i> Checkout
        </button>
      </div>
      <cart />
    </div>
    <app-top-nav></app-top-nav>
    <b-navbar toggleable="lg">
      <b-navbar-brand :href="localePath('/')" class="brand">
        <img
          src="/assets/images/logo.png"
          alt="logoImage"
          style="maxwidth: 200px"
        />
      </b-navbar-brand>

      <div class="d-flex align-items-center">
        <div class="d-flex align-items-center smallScr">
          <div class="m-0 cartIcon" @click="openCart = !openCart">
            <span>{{ $store.state.cartItems.length }}</span>
            <i class="fa-regular fa-cart-plus"></i>
          </div>
          <div v-if="$store.state.user" class="logout" @click="logout">
            <i class="fa-regular fa-right-from-bracket"></i>
          </div>
        </div>
        <b-navbar-toggle target="navbar-toggle-collapse">
          <template #default="{ expanded }">
            <span
              class="menu-trigger"
              :class="expanded ? 'active' : ''"
              id="menu03"
            >
              <span></span>
              <span></span>
              <span></span>
            </span>
          </template>
        </b-navbar-toggle>
      </div>
      <b-collapse
        id="navbar-toggle-collapse"
        class="ml-auto justify-content-end"
        is-nav
      >
        <b-navbar-nav class="align-items-center">
          <b-nav-item
            active-class="active"
            :to="localePath(`/${item.link}`)"
            exact
            v-for="item in $store.state.topMenu"
            :key="item.id"
          >
            <span v-if="!item.child.length">{{ item.label }}</span>

            <b-dropdown
              :text="item.label"
              block
              class="m-2 dropdownBtn"
              v-if="item.child.length"
            >
              <b-dropdown-item
                v-for="child in item.child"
                :key="child.id"
                :to="localePath('/' + child.link)"
                >{{ child.label }}</b-dropdown-item
              >
            </b-dropdown>
          </b-nav-item>
          <b-nav-item v-if="$store.state.user" @click="logout" class="outLarge">
            Logout
          </b-nav-item>
        </b-navbar-nav>
      </b-collapse>
      <div class="d-flex align-items-center largeScr">
        <div class="m-0 cartIcon" @click="openCart = !openCart">
          <span>{{ $store.state.cartItems.length }}</span>
          <i class="fa-regular fa-cart-plus"></i>
        </div>
        <div v-if="$store.state.user" class="logout" @click="logout">
          <i class="fa-regular fa-right-from-bracket"></i>
        </div>
      </div>
    </b-navbar>
  </header>
</template>

<script>
import cart from "../cart/cart.vue";
import AppTopNav from "./AppTopNav.vue";
// import DropdownMenu from '@innologica/vue-dropdown-menu'
export default {
  name: "AppHeader",
  components: {
    AppTopNav,
    cart,
    // DropdownMenu
  },
  data() {
    return {
      show: false,
      show1: false,
      topOfPage: true,
      openCart: false,
    };
  },
  beforeMount() {
    window.addEventListener("scroll", this.handleScroll);
  },
  mounted() {},
  methods: {
    logout() {
      this.$swal({
        title: "Logout!",
        text: "Are you sure? You want to logout from your account!",
        type: "warning",
        showCancelButton: true,
        confirmButtonColor: "#ff5e57",
        confirmButtonText: "Logout",
      }).then((result) => {
        if (result.value) {
          this.confirmLogout();
        }
      });
    },
    confirmLogout() {
      this.$store.commit("setUserData", null);
      this.$cookies.remove("cms-auth");
      this.$cookies.remove("cms-user");
      this.$router.push(this.localePath("/login"));
    },
    handleScroll() {
      if (window.pageYOffset > 200) {
        if (this.topOfPage) this.topOfPage = false;
      } else {
        if (!this.topOfPage) this.topOfPage = true;
      }
    },
    goToCheckout() {
      this.openCart = false;
      this.$router.push("/checkout");
    },
  },
};
</script>
<style lang="scss">
.swal2-container {
  padding: 0 !important;
}
.swal2-shown {
  padding: 0 !important;
}
.swal2-confirm:focus,
.swal2-cancel:focus {
  box-shadow: none !important;
}
.swal2-cancel {
  background: #e5e5e5 !important;
  color: rgb(51, 51, 51) !important;
}
header {
  background-position: left top;
  background-repeat: no-repeat;
  border-width: 0px;
  border-style: solid;
  background-size: cover;
  background-image: url("https://avada.theme-fusion.com/financial-advisor/wp-content/uploads/sites/145/2020/08/subpage-header-bg-vector.svg");
  padding-top: 0px;
  margin-top: 0px;
  padding-right: 30px;
  padding-bottom: 0px;
  margin-bottom: 0px;
  padding-left: 30px;
  z-index: 5000 !important;
  position: relative;
  .cart {
    width: 390px;
    height: 100vh;
    position: fixed;
    top: 0;
    right: 0;
    transform: translateX(390px);
    background-color: #fff;
    z-index: 999999;
    box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.2);
    .head {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 10px;
      & > i {
        border: 1px solid var(--main-color);
        border-radius: 5px;
        width: 30px;
        height: 30px;
        display: grid;
        place-items: center;
        cursor: pointer;
        background-color: var(--main-color);
        color: #fff;
        &:hover {
          color: var(--main-color);
          background: transparent;
        }
      }
      button {
        padding: 5px 30px;
        font-size: 1.1rem;
        background-color: var(--main-color);
        color: #fff;
        border: 1px solid var(--main-color);
        display: flex;
        align-items: center;
        gap: 5px;
        i {
          font-size: 1.1rem;
        }
        &:disabled {
          opacity: 0.5;
          cursor: not-allowed;
          &:hover {
            background-color: var(--main-color);
            color: #fff;
          }
        }
        &:hover {
          background-color: transparent;
          color: var(--main-color);
        }
      }
    }
    &.opened {
      transform: translateX(0);
    }
    @include xs {
      width: 350px;
    }
  }
  .cartIcon {
    border: 1px solid #fff;
    border-radius: 5px;
    width: 45px;
    height: 45px;
    display: grid;
    place-items: center;
    cursor: pointer;
    position: relative;
    margin: 0 10px !important;
    span {
      position: absolute;
      top: -15px;
      right: -10px;
      width: 30px;
      height: 30px;
      background-color: var(--main-color);
      border-radius: 50%;
      color: #fff;
      display: grid;
      place-content: center;
      font-size: 1.2rem;
      @include sm {
        font-size: 1rem;
      }
    }
    i {
      color: #fff;
    }
    @include sm {
      width: 40px;
      height: 40px;
      margin: 0 10px !important;
    }
    &:hover {
      background-color: var(--main-color);
      border-color: var(--main-color);
      i {
        color: #fff;
      }
    }
  }
}
.logout {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background-color: #fff;
  color: var(--main-color);
  display: grid;
  place-items: center;
  font-size: 1.2rem;
  cursor: pointer;
  @include md {
    display: none;
  }
}
.outLarge {
  display: none !important;
  @include md {
    display: inline !important;
  }
}
.smallScr {
  align-items: center;
  display: none !important;
  @include md {
    display: flex !important;
  }
}
.largeScr {
  align-items: center;
  display: flex !important;
  @include md {
    display: none !important;
  }
}
.brand {
  img {
    @include sm {
      width: 180px;
    }
  }
}
.navbar-brand img {
  max-height: 49px;
  height: auto;
}
.nav-item {
  position: relative;
  margin-right: calc(40px / 2);
  text-transform: uppercase;
  display: flex;
  justify-content: center;
  transition: all calc(300 * 1ms) cubic-bezier(0.42, 0.01, 0.58, 1);
  font-size: 15px;
  & > .dropdown {
    display: none;
  }
}
.nav-item {
  @include md {
    a {
      width: 100%;
      display: block;
      text-align: center;
    }
    button {
      color: #000 !important;
    }
  }
}
.nav-link {
  padding: 0 !important;
  font-weight: 800;
  font-size: 15px;
  line-height: 27px;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  transition: color calc(300 * 1ms) cubic-bezier(0.42, 0.01, 0.58, 1),
    background-color calc(300 * 1ms) cubic-bezier(0.42, 0.01, 0.58, 1);
  z-index: 10;
  color: #fff;
}
.active .nav-link,
.nav-link:hover {
  color: rgb(81, 229, 165);
}

.navbar-toggler,
.navbar-toggler:focus {
  border: none;
  box-shadow: none;
}
.menu-trigger,
.menu-trigger span {
  display: inline-block;
  transition: all 0.4s;
  box-sizing: border-box;
}
.menu-trigger {
  position: relative;
  width: 32px;
  height: 25px;
  background: none;
  border: none;
  appearance: none;
  cursor: pointer;
}
.menu-trigger span {
  position: absolute;
  left: 0;
  width: 100%;
  height: 5px;
  background-color: #fff;
  border-radius: 4px;
}
.menu-trigger span:nth-of-type(1) {
  top: 0;
}
.menu-trigger span:nth-of-type(2) {
  top: 10px;
}
.menu-trigger span:nth-of-type(3) {
  bottom: 0;
}
#menu03.active {
  transform: rotate(360deg);
}
#menu03.active span:nth-of-type(1) {
  transform: translateY(10px) rotate(-45deg);
}
#menu03.active span:nth-of-type(2) {
  transform: translateY(0) rotate(45deg);
}
#menu03.active span:nth-of-type(3) {
  opacity: 0;
}

@media screen and (max-width: 991px) {
  .navbar-collapse.show .navbar-nav {
    position: absolute;
    width: 250px;
    top: 56px;
    right: 0;
  }
  .nav-item {
    width: 100%;
    border-bottom: 1px solid #e5e5e5;
    background: #fff;
  }
  .nav-item .nav-link {
    color: #000;
  }
  .nav-item:after {
    content: none;
  }
  .nav-item.active,
  .nav-item:hover {
    background-color: #535ee5;
  }
  .nav-item.active .nav-link,
  .nav-item:hover .nav-link {
    color: #fff;
  }
  .nav-link {
    padding: 8px 20px !important;
    font-weight: 800;
    font-size: 15px;
    text-align: right;
  }
}
.dropdownBtn {
  margin: 0 !important;
  button {
    background: none !important;
    padding: 0 !important;
    text-transform: uppercase !important;
    font-size: 1rem !important;
    font-family: unset !important;
    font-weight: 700 !important;
    box-shadow: none !important;
    border: none !important;
    min-width: unset !important;
    width: 100%;
    min-height: 30px;
    position: relative;
    top: -3px;
  }
  .dropdown-menu {
    top: 40px !important;
    left: -50px;
  }
}
</style>
