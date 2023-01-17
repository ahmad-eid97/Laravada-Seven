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
<style></style>
