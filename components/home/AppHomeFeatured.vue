<template>
  <div class="featured">
    <h2>As Featured In</h2>
    <div class="row mx-0 justify-content-center" v-if="partners.length >= 1">
      <div
        v-for="partner in partners"
        :key="partner"
        class="col-sm-6 col-md-4 col-lg-2 brand"
      >
        <img :src="partner.image" :alt="partner.title" />
        <h5>{{ partner.title }}</h5>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "AppHomeFeatured",
  props: ["partners"],
  data() {
    return {};
  },
};
</script>
<style>
.featured {
  padding-top: 50px;
  margin-top: 0px;
  padding-right: 30px;
  padding-bottom: 0;
  margin-bottom: 0px;
  padding-left: 30px;
  text-align: center;
}
.featured h2 {
  color: rgb(33, 41, 52);
  font-size: 35px;
  font-weight: 900;
  line-height: 42px;
  letter-spacing: -1px;
  margin-bottom: 20px;
}
.featured .brand {
  /* margin-bottom: 20px;
        margin-left: 24px;
        margin-right: 24px; */
  /* width: 450px; */
  height: 165px;
  filter: opacity(80%);
}
.featured .brand img {
  max-width: 100%;
  height: 80px;
  object-fit: contain;
}
.featured .brand:hover {
  filter: opacity(100%);
}
</style>
