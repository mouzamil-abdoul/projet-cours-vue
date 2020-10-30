<template>
  <div class="border border-orange-500 rounded w-1/5 mx-auto text-center">
    Mon panier contient {{ selection.length }}
    <span v-if="nbrCours">cours</span>
    <span v-else>cours</span>
  </div>
</template>

<script>
export default {
  name: "selection-basket",
  props: ["selection"],
  computed: {
    nbrCours() {
      if (this.selection.length > 1) {
        return true;
      }
      return false;
    },
  },
};
</script>

<style></style>
