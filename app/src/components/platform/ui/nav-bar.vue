<template>
  <div
    class="hidden px-4 bg-green-400 dark:bg-purple-950 py-2 w-full justify-between md:flex items-center"
  >
    <div>
      <Logo size="h-9" />
    </div>
    <div class="flex items-center gap-4">
      <Notifications v-if="account" />
      <UserMenu />
    </div>
  </div>
</template>

<script>
import Notifications from "@/components/platform/ui/notifications.vue";
import UserMenu from "@/components/platform/ui/user-menu.vue";
import Logo from "@/components/ui/logo.vue";

export default {
  components: {
    Notifications,
    UserMenu,
    Logo,
  },
  computed: {
    account() {
      return this.$store.state.account;
    },
  },
};
</script>
