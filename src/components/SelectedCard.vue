<template>
  <div
    class="border border-black-900 m-2 p-2 rounded relative"
    :class="isFrontClass"
  >
    <h3 class="text-lg font-bold">{{ course.name }}</h3>

    <img :src="courseImage(course.image)" alt="" class="w-64" />
    <p>
      Il s'agit d'un cours
      <span v-if="nbrCours"> d'{{ course.duration }} heure.</span>
      <span v-else> de {{ course.duration }} heures.</span>
    </p>
  </div>
</template>

<script>
export default {
  name: "selected-card",
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
    courseImage(img) {
      return require("@/assets/img/" + img);
    },
  },
};
</script>

<style></style>
