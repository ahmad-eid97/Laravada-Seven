<template>
  <div class="team-area pt-100 pb-70">
    <div class="container">
      <div class="section-title text-center">
        <span class="sp-color2">Our Team</span>
        <h2>Our Team Members</h2>
        <div class="seprator">
          <img
            src="https://avada.theme-fusion.com/financial-advisor/wp-content/uploads/sites/145/2020/08/slant-separator.png"
            alt=""
          />
        </div>
      </div>
      <div class="row pt-45" v-if="team.teams.length >= 1">
        <div
          v-for="member in team.teams"
          :key="member.id"
          class="col-sm-6 col-md-4 projects-col"
        >
          <div class="card">
            <div class="thumb">
              <img :src="member.image" alt="" />
              <div class="rollover"></div>
            </div>
            <div class="content">
              <h4>{{ member.name }}</h4>
              <h5>{{ member.job }}</h5>
              <h6>
                {{ member.description.substring(0, 200) }}
                {{ member.description.length > 200 ? "..." : "" }}
              </h6>
              <h5>{{ member.phone }}</h5>
              <h5>{{ member.email }}</h5>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "AppTestimonialsTeam",
  props: ["team"],
};
</script>

<style>
.team-area .section-title {
  margin-bottom: 0;
}
.team-area .section-title span {
  margin-bottom: 8px;
  font-weight: 600;
  display: block;
  color: #51e5a5;
}
.team-area .section-title h2 {
  max-width: 600px;
  color: #212934;
  font-size: 35px;
  font-weight: 800;
  letter-spacing: -1px;
  line-height: 42px;
  text-align: left;
  margin-top: 10px;
  margin-right: auto;
  margin-bottom: 15px;
  margin-left: auto;
  text-align: center;
}
.team-area .section-title .seprator img {
  width: 70px;
  margin-top: 5px;
  margin-bottom: 20px;
}
.thumb img {
  width: 100%;
  height: 250px;
}
.card .content {
  padding: 20px;
  text-align: center !important;
}
</style>
