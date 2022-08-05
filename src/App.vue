<template lang="">
  <div>
    <Suspense>
      <template #default><Home /></template>
      <template #fallback><SplashScreenVue /></template>
    </Suspense>
  </div>
</template>
<script>
import Home from "./components/Home.vue";
import SplashScreenVue from "./components/SplashScreen.vue";

import { defineAsyncComponent } from "vue";
export default {
  components: {
    SplashScreenVue,
    Home: defineAsyncComponent(
      () =>
        new Promise((resolve, reject) => {
          setTimeout(() => {
            resolve(import("./components/Home.vue"));
          }, 2500);
        })
    ),
  },
};
</script>
<style>
html,
body,
.app {
  min-height: 100vh;
  margin: 0;
  font-family: Arial, Helvetica, sans-serif;
}
* {
  --brand-green: #04b500;
  --brand-blue: #0689b0;
}
</style>
