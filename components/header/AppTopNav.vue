<template>
  <div class="row mx-0 top-nav justify-content-end">
    <div class="col-auto contact">
      <ul class="d-flex align-items-center">
        <li>
          <a href="#">
            <i class="fa-regular fa-envelope"></i>

            <span class="menu-text">info@railcoder.com</span>
          </a>
        </li>
        <li>
          <a href="#">
            <i class="fa-solid fa-phone"></i>
            <span class="menu-text">+1111111111</span>
          </a>
        </li>
        <li>
          <a href="#">
            <i class="fa-regular fa-clock"></i>
            <span class="menu-text">Available Mon-Fri: 8:00AM – 6:00PM</span>
          </a>
        </li>
        <span><langSwitch></langSwitch></span>
      </ul>
    </div>
    <a
      href="/qoutation"
      class="btn col-auto largeBtn"
      @click="$router.push('/qoutation')"
      >Get Qoutation</a
    >
    <div class="smallTop">
      <a
        href="/qoutation"
        class="btn col-auto"
        @click="$router.push('/qoutation')"
        >Get Qoutation</a
      >
      <span><langSwitch></langSwitch></span>
    </div>
  </div>
</template>

<script>
import langSwitch from "../langSwitch/langSwitch.vue";
export default {
  name: "AppTopNav",
  data() {
    return {};
  },
  components: {
    langSwitch,
  },
};
</script>

<style lang="scss">
@include md {
  .contact {
    display: none;
  }
}
.top-nav {
  margin-bottom: 20px;
}
.largeBtn {
  @include md {
    display: none;
  }
}
.smallTop {
  display: none;
  @include md {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 50px;
  }
}
.top-nav .btn {
  padding: 13px 29px;
  color: rgb(33, 41, 52);
  background-color: rgb(81, 229, 165);
  margin-right: 24px;
  margin-left: 0%;
  border-radius: 0px 0px 6px 0px;
  border: none;
  font-size: 14px;
  line-height: 18px;
  font-weight: 800;
}
.top-nav .btn:hover {
  color: rgb(255, 255, 255);
  background-color: rgb(83, 94, 229);
  border: none;
}
.top-nav .contact {
  background-color: rgb(52, 41, 173);
  border-bottom-left-radius: 6px;
  margin-left: 24px;
}
.top-nav .contact ul {
  display: flex;
  flex-wrap: wrap;
  align-items: stretch;
  list-style: none;
  justify-content: flex-start;
  flex-direction: row;
  padding: 0;
  font-family: inherit;
  font-weight: 400;
  margin-block-start: 0;
  margin-block-end: 0;
  position: relative;
  transition: all calc(300 * 1ms) cubic-bezier(0.42, 0.01, 0.58, 1);
  text-transform: none;
  justify-content: space-around;
  font-weight: 400;
}
.top-nav .contact ul li {
  padding: 8px 30px 10px;
}
.top-nav .contact ul a {
  font-size: 11px;
  color: #fff;
  text-decoration: none;
  font-weight: 700;
}
.top-nav .contact ul a i {
  padding: 0 0.5em;
  font-size: 12px;
  max-width: 25px;
}
</style>
