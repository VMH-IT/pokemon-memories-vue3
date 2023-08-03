<template>
  <main-screen v-if="statusMatch === 'default'" @onStart="onHandleBeforeStart($event)" />
  <interact-screen v-if="statusMatch === 'match'" />
</template>

<script>
import MainScreen from "./components/MainScreen.vue";
import InteractScreen from "./components/InteractScreen.vue";
// import FooterScreen from "./components/FooterScreen.vue";
// import ResultScreen from "./components/FooterScreen.vue";

export default {
  name: "App",
  data() {
    return {
      statusMatch: "default",
    };
  },

  components: {
    MainScreen,
    // FooterScreen,
    InteractScreen,
    // ResultScreen
  },
  methods: {
    onHandleBeforeStart(config) {
      console.log("running ...", config);
      this.statusMatch = "match"
    }
  }
};
</script>
