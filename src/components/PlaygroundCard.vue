<template>
  <div class="playground-card">
    <div class="icon-wrapper">
      <SvgIcon :name="cardicon" />
    </div>
    <h1 class="title">{{ title }}</h1>
    <h3 class="detail" v-for="item in details" :key="item">
      {{ item }}
    </h3>
  </div>
</template>

<script>
import SvgIcon from "./svgIcon.vue";

export default {
  name: "PlaygroundCard",
  components: {
    SvgIcon: SvgIcon,
  },
  props: {
    title: String,
    details: Array,
    cardicon: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.playground-card {
  min-width: 120px;
  padding: 1rem;

  background: #505785;
  box-shadow: 0px 2px 4px 2px #1D1F30;
  border-radius: 1.25rem;

  flex: 1;
}

.icon-wrapper {
  width: 70px;
  height: 70px;
  border-radius: 35px;
  margin: 0 auto 1rem auto;

  background: #7680C4;
}

svg[data-v-7b86afca] {
  width: 40px;
  height: 100%;
}

.title,
.detail {
  font-family: "Poppins";
  font-style: normal;
  font-weight: 300;
  font-size: 13px;
  line-height: 15px;
  text-align: center;

  color: #FFFFFF;
}

.title {
  font-weight: 600;
  font-size: 18px;
  line-height: 18px;
  margin-bottom: 0.75rem;
}

.detail {
  color: white;
  margin-bottom: 0.25rem;
}

.detail:last-child {
  margin-top: 0;
  margin-bottom: 0;
}
</style>
