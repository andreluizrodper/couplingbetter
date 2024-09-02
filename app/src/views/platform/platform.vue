<template>
  <CreateCouple v-if="!account.inCouple" />
  <div v-if="account.inCouple" class="flex flex-1 w-full">
    <div class="flex flex-1 w-full flex-col">
      <div class="mx-auto w-full max-w-4xl flex gap-4 flex-1 my-3 px-3">
        <Sidebar />
        <RouterView />
      </div>
      <Footer />
    </div>
  </div>
</template>

<script>
import CreateCouple from "@/components/platform/create-couple.vue";
import Feed from "@/components/platform/feed.vue";
import { RouterView } from "vue-router";
import Sidebar from "@/components/platform/ui/sidebar.vue";
import Footer from "@/components/platform/ui/footer.vue";

export default {
  components: {
    CreateCouple,
    Feed,
    RouterView,
    Sidebar,
    Footer,
  },
  computed: {
    account() {
      return this.$store.state.account;
    },
  },
};
</script>
