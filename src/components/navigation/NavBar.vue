<template>
  <div class="bg-orange-500 text-white py-5 px-2">
    <a
      v-for="(link, index) in navigation"
      :key="index"
      href="#"
      class="border border-white-900 mx-2 p-2 rounded"
      @click="selectComponent(link.component)"
      >{{ link.name }}
    </a>
  </div>
</template>

<script>
export default {
  name: "nav-bar",
  data() {
    return {
      navigation: [
        { name: "Tous les cours", component: "course-list" },
        { name: "Mes cours", component: "selected-list" },
      ],
    };
  },
  methods: {
    selectComponent(comp) {
      this.$emit("change-component", comp);
    },
  },
};
</script>

<style></style>
