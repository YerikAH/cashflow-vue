<template>
  <header>
    <img @click="reload" src="../assets/logo.svg" alt="logo-cute" />
    <h1>Cash <span>Flow</span></h1>
    <span></span>
  </header>
</template>
<script>
export default {
  methods: {
    reload() {
      location.reload(true);
    },
  },
};
</script>
<style scoped>
header {
  display: flex;
  justify-content: space-around;
  align-items: center;
  width: 100vw;
}
img,
span {
  width: 48px;
}
h1 {
  font-size: 1.4rem;
  color: var(--brand-blue);
}
h1 span {
  color: var(--brand-green);
}
</style>
