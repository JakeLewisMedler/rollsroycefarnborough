<template>
  <div class="layout">
    <Nuxt v-if="$global.loaded" />
  </div>
</template>
<script>
export default {
  async mounted() {
    await this.$socket.init();
    await this.$global.init();
    await this.$global.getScreens();
    console.log(this.$global);
    this.$global.loaded = true;
  },
};
</script>
<style lang="scss">
.layout {
}
</style>
