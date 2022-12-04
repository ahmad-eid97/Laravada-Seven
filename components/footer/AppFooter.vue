<template>
  <footer>
    <div class="row mx-0">
      <div class="col navigate">
        <div class="row mx-0">
          <div class="col-auto">
            <h2>Navigate</h2>
            <ul>
              <li>
                <nuxt-link :to="localePath('/contact')"> CONTACT </nuxt-link>
              </li>
              <li>
                <nuxt-link :to="localePath('/faq')"> FAQS </nuxt-link>
              </li>
              <li>
                <nuxt-link :to="localePath('/policy')"> PRIVACY </nuxt-link>
              </li>
              <li>
                <nuxt-link :to="localePath('/terms')"> TERMS </nuxt-link>
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
                  <span class="menu-text">0800 000 000</span>
                </a>
              </li>
              <li>
                <a href="#">
                  <i class="fa-regular fa-clock"></i>
                  <span class="menu-text"
                    >Available Mon-Fri: 8:00AM – 6:00PM</span
                  >
                </a>
              </li>
            </ul>
            <p>
              Don‘t call us, we‘ll call you. Request a callback, just drop your
              phone number in the form below and hit the request.
            </p>
            <form class="intro-form">
              <b-form-input
                id="input-1"
                type="tel"
                placeholder="Telephone Number"
              >
              </b-form-input>
              <a href="#" class="btn col-12">REQUEST CALLBACK</a>
            </form>
          </div>
        </div>
      </div>
      <div class="col-auto logo">
        <img
          src="/assets/images/logo.png"
          alt="logoImage"
          style="width: 200px; marginbottom: 25px"
        />
        <div class="col-12 text-end">
          <a
            :href="`https://${$store.state.footerData.instagram}`"
            target="_blank"
          >
            <i class="fa-brands fa-instagram"></i>
          </a>
          <a
            :href="`https://${$store.state.footerData.twitter}`"
            target="_blank"
          >
            <i class="fa-brands fa-twitter"></i>
          </a>
          <a
            :href="`https://${$store.state.footerData.facebook}`"
            target="_blank"
          >
            <i class="fa-brands fa-facebook-f"></i>
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
export default {
  name: "AppFooter",
  components: {},
  data() {
    return {};
  },
  methods: {},
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
