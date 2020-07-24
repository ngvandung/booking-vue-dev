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
          {
            title: "Dashboard",
            router: "/manager/dashboard",
            icon: "dashboard",
          },
          {
            title: "Account Setting",
            router: "/manager/edit-account/profile",
            icon: "account_circle",
          },
          {
            title: "Host Pending",
            router: "/manager/hosts",
            icon: "supervisor_account",
          },
          {
            title: "Home Pending",
            router: "/manager/homes",
            icon: "home",
          },
        ],
      },
    };
  },
  beforeMount: function () {
    let vm = this;
    if (
      localStorage.getItem("isSign") != "true" ||
      localStorage.getItem("roleName") != "ROLE_MANAGER"
    ) {
      vm.$router.replace("/error/403");
    }
  },
};
</script>

<style>
</style>