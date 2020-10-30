<template>
  <div
    class="border border-black-900 m-2 p-2 rounded relative"
    :class="isFrontClass"
  >
    <h3 class="text-lg font-bold">{{ course.name }}</h3>
    <p>
      Il s'agit d'un cours de développement {{ course.stack }}
      <span v-if="nbrCours"> d'{{ course.duration }} heure.</span>
      <span v-else> de {{ course.duration }} heures.</span>
    </p>
    <base-button text="Ajoute ce cours" @click="addToSelection"></base-button>
  </div>
</template>

<script>
export default {
  name: "course-card",
  props: ["course"],
  computed: {
    nbrCours() {
      if (this.course.duration == "1") {
        return true;
      }
      return false;
    },
    courseFront() {
      if (this.course.stack == "front") {
        return true;
      }
      return false;
    },
    isFrontClass() {
      return {
        "bg-yellow-300": this.courseFront,
        "bg-teal-300": !this.courseFront,
      };
    },
  },
  methods: {
    addToSelection() {
      this.$emit("add-course", this.course);
    },
  },
};
</script>

<style></style>
