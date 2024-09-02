<template>
  <div class="flex flex-col flex-1 min-h-[100vh]">
    <NameDialog v-if="!hasData" />
    <NavBar />
    <div v-if="account" class="flex flex-1">
      <RouterView />
    </div>
    <Dialog />
  </div>
</template>

<script>
import { RouterView } from "vue-router";
import NavBar from "@/components/platform/ui/nav-bar.vue";
import Dialog from "@/components/ui/dialog.vue";
import NameDialog from "@/components/platform/name-dialog.vue";

export default {
  components: {
    RouterView,
    NavBar,
    Dialog,
    NameDialog,
  },
  computed: {
    account() {
      return this.$store.state.account;
    },
    hasData() {
      return this.account.name?.length > 0 && this.account.avatar?.length;
    },
  },
  async mounted() {},
};
</script>
