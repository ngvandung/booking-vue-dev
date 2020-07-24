<template>
  <v-app>
    <base-view />
  </v-app>
</template>

<script>
export default {
  name: "HostLayout",
  components: {
    BaseView: () => import("@/components/BaseView")
  },
  beforeCreate: function() {
    let vm = this;
    if (localStorage.getItem("isSign") != "true") {
      vm.$router.replace("/error/403");
    }
  }
};
</script>

<style>
</style>