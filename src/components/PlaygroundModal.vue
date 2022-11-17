<template>
  <div class="centered-card">
    <div
      class="title-wrapper"
      :class="{ 'accessibility-available': playground.accessibility }"
    >
      <h1>{{ playground.title }}</h1>
    </div>
    <div v-if="playground.accessibility" class="accessibility-wrapper">
      <div>Barrierefrei</div>
    </div>
    <div class="header-details">
      <h3 v-for="subtitle in playground.subtitles" :key="subtitle">
        {{ subtitle }}
      </h3>
    </div>
    <div class="playgroundgear-wrapper">
      <PlaygroundCard
        v-for="item in playground.playgroundgear"
        :key="item.title"
        :title="item.title"
        :details="item.details"
        :cardicon="item.cardicon"
      />
    </div>
  </div>
</template>

<script setup>
import PlaygroundCard from "./PlaygroundCard.vue";

export default {
  name: "App",
  components: {
    PlaygroundCard: PlaygroundCard,
  },
  props: {
    playground: Object,
  },
};
</script>

<style>
h1,
h2,
h3,
.accessibility-wrapper {
  font-family: "Poppins";
  font-style: normal;
  font-weight: 400;
  line-height: 15px;
  text-align: left;
}

.title-wrapper,
.header-details {
  width: 100%;
}
.title-wrapper h1 {
  font-weight: 600;
  font-size: 1.5rem;
  line-height: 1.5rem;
  color: #FFFFFF;
  margin: 1.5rem 0 1.5rem 0;
}

.title-wrapper.accessibility-available h1 {
  margin-bottom: 0.5rem;
}

.header-details h3 {
  font-size: 20px;
  letter-spacing: 1px;
  color: #C3C5D5;
  margin-bottom: 1rem;
}

.accessibility-wrapper {
  width: 100%;
  height: 2rem;
  display: flex;
  justify-content: flex-end;
  line-height: 2rem;

  color: #FFFFFF;
}
.accessibility-wrapper div {
  background-color: #53209E;
  padding-left: 1rem;
  border-radius: 1rem 0 0 1rem;
  margin-right: -1.5rem;
}
.accessibility-wrapper div:after {
  content: "";
  height: 2rem;
  margin-right: 1.5rem;
}

.centered-card {
  height: 495px;
  background-color: #212437;
  margin: 0 auto;
  padding: 1.5rem;
  border-radius: 2.5rem 2.5rem 0px 0px;
  overflow: scroll;
}

.playgroundgear-wrapper {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-evenly;
  align-content: flex-start;
  gap: 1.5rem;
}
</style>
