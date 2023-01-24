<template>
  <div class="home">
    <app-home-intro></app-home-intro>
    <app-home-featured :partners="partners"></app-home-featured>
    <app-home-features
      :testimonials="testimonials"
      :faqs="faqs"
    ></app-home-features>
    <app-home-activities :activities="activities" />
    <app-home-steps :steps="steps" />
    <app-home-work :services="services"></app-home-work>
    <SocialChat :attendants="attendants">
      <p slot="header">Click one of our representatives below to chat.</p>
      <template v-slot:button="{ open }">
        <span v-show="!open">Contact us</span>
        <span v-show="open">Close</span>
      </template>
      <small slot="footer">Opening hours: 8am to 10pm</small>
    </SocialChat>
  </div>
</template>

<script>
// import AppHomeBottomBanner from '../components/home/AppHomeBottomBanner.vue'
// import AppHomeCount from '../components/home/AppHomeCount.vue'
import AppHomeFeatured from "../components/home/AppHomeFeatured.vue";
import AppHomeFeatures from "../components/home/AppHomeFeatures.vue";
import AppHomeIntro from "../components/home/AppHomeIntro.vue";
import AppHomeWork from "../components/home/AppHomeWork.vue";
import AppHomeActivities from "../components/home/AppHomeActivities.vue";
import AppHomeSteps from "../components/home/AppHomeSteps.vue";
// import AppHomeNews from '../components/home/AppHomeNews.vue'
// import AppHomePartners from '../components/home/AppHomePartners.vue'
// import AppHomeTestominials from '../components/home/AppHomeTestominials.vue'
// import AppHomeValues from '../components/home/AppHomeValues.vue'
// import AppHomeWork from '../components/home/AppHomeWork.vue'

export default {
  name: "Home",
  data() {
    return {
      attendants: [
        {
          app: "whatsapp",
          label: "Support",

          name: this.$store.state.websiteSettings.find(
            (one) => one.key === "chat_widget_whatsapp_label"
          )
            ? this.$store.state.websiteSettings.find(
                (one) => one.key === "chat_widget_whatsapp_label"
              ).plain_value
            : "Laravada",

          number: this.$store.state.websiteSettings.find(
            (one) => one.key === "chat_widget_whatsapp_number"
          )
            ? this.$store.state.websiteSettings.find(
                (one) => one.key === "chat_widget_whatsapp_number"
              ).plain_value
            : "11111111111",

          avatar: {
            src: "https://avatars0.githubusercontent.com/u/8084606?s=460&u=20b6499a416cf7129a18e5c168cf387e159edb1a&v=4",
            alt: "Laravada customer support",
          },
        },
        {
          app: "messenger",
          label: "Technical support",

          name: this.$store.state.websiteSettings.find(
            (one) => one.key === "chat_widget_messenger_label"
          )
            ? this.$store.state.websiteSettings.find(
                (one) => one.key === "chat_widget_messenger_label"
              ).plain_value
            : "Laravada Facebook",

          id: this.$store.state.websiteSettings.find(
            (one) => one.key === "chat_widget_messenger_id"
          )
            ? this.$store.state.websiteSettings.find(
                (one) => one.key === "chat_widget_messenger_id"
              ).plain_value
            : "111111111111",

          avatar: {
            src: "https://avatars0.githubusercontent.com/u/8084606?s=460&u=20b6499a416cf7129a18e5c168cf387e159edb1a&v=4",
            alt: "Laravada customer support",
          },
        },
      ],
    };
  },
  async asyncData({ $axios, app }) {
    const testimonials = await $axios.get("/testimonials");

    const partners = await $axios.get("/partners");

    const faqs = await $axios.get("/faqs");

    const services = await $axios.get("/services");

    const activities = await $axios.get("/sections/activities", {
      headers: {
        "Accept-Language": app.i18n.locale,
      },
    });

    const steps = await $axios.get("/sections/steps", {
      headers: {
        "Accept-Language": app.i18n.locale,
      },
    });

    return {
      testimonials: testimonials.data.data.testimonials,
      partners: partners.data.data.partners,
      faqs: faqs.data.data.fags,
      services: services.data.data.services,
      activities: activities.data.data,
      steps: steps.data.data,
    };
  },
  components: {
    AppHomeIntro,
    AppHomeFeatured,
    AppHomeFeatures,
    AppHomeWork,
    AppHomeActivities,
    AppHomeSteps,
  },
};
</script>
<style>
.home {
  --vsc-bg-header: var(--main-color);
  --vsc-bg-footer: var(--main-color);
  --vsc-text-color-header: #fff;
  --vsc-text-color-footer: #fff;
  --vsc-bg-button: var(--main-color);
  --vsc-text-color-button: #fff;
  --vsc-outline-color: var(--main-color);
  --vsc-border-color-bottom-header: #fff;
  --vsc-border-color-top-footer: #fff;
}
</style>
