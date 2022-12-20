<template>
  <header>
    <app-top-nav></app-top-nav>
    <b-navbar toggleable="lg">
      <b-navbar-brand :href="localePath('/')">
        <img
          src="/assets/images/logo.png"
          alt="logoImage"
          style="maxwidth: 250px"
        />
      </b-navbar-brand>

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

      <b-collapse
        id="navbar-toggle-collapse"
        class="ml-auto justify-content-end"
        is-nav
      >
        <b-navbar-nav class="align-items-center">
          <b-nav-item :to="localePath('/')">Home</b-nav-item>
          <b-nav-item :to="localePath('/about')">About</b-nav-item>
          <b-nav-item :to="localePath('/testimonials')">Rates</b-nav-item>
          <b-nav-item :to="localePath('/services')">Webinar</b-nav-item>
          <b-nav-item :to="localePath('/blogs')">Articles</b-nav-item>
          <b-nav-item :to="localePath('/careers')">Career</b-nav-item>
          <b-nav-item :to="localePath('/events')">Events</b-nav-item>
          <b-nav-item :to="localePath('/contact')">Contact Us</b-nav-item>
          <div v-if="$store.state.user" class="logout" @click="logout">
            <i class="fa-regular fa-right-from-bracket"></i>
          </div>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </header>
</template>

<script>
import AppTopNav from "./AppTopNav.vue";
// import DropdownMenu from '@innologica/vue-dropdown-menu'
export default {
  name: "AppHeader",
  components: {
    AppTopNav,
    // DropdownMenu
  },
  data() {
    return {
      show: false,
      show1: false,
      topOfPage: true,
    };
  },
  beforeMount() {
    window.addEventListener("scroll", this.handleScroll);
  },
  mounted() {},
  methods: {
    logout() {
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
  },
};
</script>
<style>
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
</style>
