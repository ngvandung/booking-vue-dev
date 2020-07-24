<template>
  <drawner-bar :tabs="tabs" />
</template>

<script>
export default {
  components: { DrawnerBar: () => import("@/components/DrawnerBar.vue") },
  data() {
    return {
      tabs: {
        items: [
          { title: "Dashboard", router: "/host/dashboard", icon: "dashboard" },
          { title: "My Homes", router: "/host/homes", icon: "home" },
          {
            title: "Account Setting",
            router: "/host/edit-account/profile",
            icon: "account_circle",
          },
          { title: "Messages", router: "/dsdsa", icon: "chat" },
        ],
      },
    };
  },
  beforeCreate: function () {
    if (
      localStorage.getItem("isSign") != "true" ||
      localStorage.getItem("roleName") != "ROLE_HOST"
    ) {
      this.$router.replace("/error/403");
    }
  },
};
</script>

<style>
</style>