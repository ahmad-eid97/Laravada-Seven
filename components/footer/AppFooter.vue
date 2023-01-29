<template>
  <footer>
    <subscribe />
    <div class="row mx-0">
      <div class="col navigate">
        <div class="row mx-0">
          <div class="col-auto">
            <h2>Navigate</h2>
            <ul class="footer-list">
              <!-- <li><a href="#">About Us</a></li> -->
              <li v-for="page in $store.state.footerPages" :key="page.id">
                <nuxt-link
                  :to="localePath(generatePagePath(page.id))"
                  v-if="page.status"
                  >{{ page.name }}</nuxt-link
                >
              </li>
            </ul>
          </div>
          <div class="col">
            <ul class="contacts">
              <li>
                <a href="#">
                  <i class="fa-regular fa-envelope"></i>

                  <span class="menu-text">{{
                    $store.state.websiteSettings.find(
                      (one) => one.key === "email"
                    ).plain_value
                  }}</span>
                </a>
              </li>
              <li>
                <a href="#">
                  <i class="fa-solid fa-phone"></i>
                  <span class="menu-text">{{
                    $store.state.websiteSettings.find(
                      (one) => one.key === "contact_phone"
                    ).plain_value
                  }}</span>
                </a>
              </li>
            </ul>
            <p>
              {{
                $store.state.websiteSettings.find(
                  (one) => one.key === "description"
                ).plain_value
              }}
            </p>
            <form class="intro-form">
              <a href="/qoutation" class="btn col-12">REQUEST QOUTATION</a>
            </form>
          </div>
        </div>
      </div>
      <div class="col-auto logo">
        <img
          :src="
            $store.state.websiteSettings.find((one) => one.key === 'logo')
              .plain_value
          "
          alt="logoImage"
          style="width: 200px; marginbottom: 25px"
        />
        <div class="col-12 text-end">
          <a
            v-for="link in $store.state.socialLinks"
            :key="link.key"
            :href="link.url"
            target="_blank"
          >
            <i :class="link.icon"></i>
          </a>
        </div>
      </div>
      <div class="col-12 copy">
        <p>
          © Copyright 2022 - 2023 | All Rights Reserved | Powered By: Rail Coder
        </p>
      </div>
    </div>
  </footer>
</template>

<script>
import Subscribe from "../subscribe/subscribe.vue";
export default {
  name: "AppFooter",
  components: { Subscribe },
  data() {
    return {};
  },
  methods: {
    generatePagePath(id) {
      switch (id) {
        case 1:
          return "/about";
        case 2:
          return "/contact";
        case 3:
          return "/terms";
        case 4:
          return "/policy";
      }
    },
  },
};
</script>
<style>
footer {
  background-color: var(--main-color);
  background-position: left top;
  background-repeat: no-repeat;
  background-blend-mode: color;
  border-width: 0px;
  border-style: solid;
  background-size: cover;
  background-image: url("https://avada.theme-fusion.com/financial-advisor/wp-content/uploads/sites/145/2020/08/footer-background-colours.i");
  overflow: hidden;
  padding-bottom: 60px;
  padding-left: 30px;
  padding-right: 30px;
}
footer .navigate {
  padding-bottom: 40px;
  padding-left: 50px;
  padding-right: 50px;
  padding-top: 30px;
  background-color: #fff;
  margin: 0 24px;
  border-bottom-left-radius: 12px;
  border-bottom-right-radius: 120px;
}
footer .navigate h2 {
  color: rgb(33, 41, 52);
  margin-top: 10px;
  margin-right: 0px;
  margin-bottom: 15px;
  margin-left: 0px;
}
footer .navigate ul {
  font-size: 13px;
  margin-top: 20px;
  padding: 0;
}
footer .navigate li {
  list-style: none;
  margin-bottom: 10px !important;
}
footer .navigate li a {
  list-style: none;
  margin-bottom: 10px !important;
  color: rgb(66, 66, 66);
  font-weight: 700;
  text-decoration: none;
}
footer .navigate li a.active,
footer .navigate li a:hover {
  color: rgb(83, 94, 229);
}

footer .contacts li {
  color: rgb(83, 94, 229);
  font-size: 12px;
  padding: 5px 0;
}
footer .contacts li i {
  margin-right: 9px;
}
footer .intro-form {
  margin-top: 40px;
  background-color: transparent;
  border-radius: 8px;
  padding: 0;
}
footer .intro-form input {
  background-color: rgb(255, 255, 255);
  border: 1px solid rgb(131, 139, 228);
  padding: 0 16px;
  height: 50px;
  font-size: 16px;
  font-weight: 700 !important;
  color: rgb(226, 226, 226) !important;
  margin: 15px 0;
}
footer .intro-form input:focus {
  box-shadow: none;
}
footer .intro-form input::placeholder {
  color: rgb(226, 226, 226) !important;
}
footer .btn {
  padding: 13px 29px;
  color: rgb(61, 61, 61);
  margin: 15px 0;
  background-color: rgb(81, 229, 165);
  border-radius: 6px;
  letter-spacing: 2px;
  border: none;
  font-size: 14px;
  line-height: 18px;
  font-weight: 800;
}
footer .btn:hover {
  color: rgb(255, 255, 255);
  background-color: rgb(83, 94, 229);
  border: none;
}

footer .logo {
  margin-right: 24px;
  padding-top: 46px;
}
footer .logo a {
  color: #fff;
  margin: 10px;
  text-decoration: none;
}
footer .copy {
  margin: 0 24px 20px;
  padding: 15px 0;
}
footer .copy p {
  margin: 14px 0;
  font-size: 14px;
  color: #fff;
}
</style>
