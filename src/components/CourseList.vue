<template>
  <h1 class="text-xl font-bold text-center p-3">{{ coursesData.name }}</h1>
  <selection-basket :selection="selection"></selection-basket>
  <course-card
    v-for="(course, index) in coursesData.cours"
    :key="index"
    :course="course"
    @add-course="addCourseToSelection"
  ></course-card>
</template>

<script>
import coursesData from "../assets/data/courses.json";
import SelectionBasket from "./SelectionBasket";
import CourseCard from "./CourseCard";
export default {
  name: "course-list",
  components: {
    SelectionBasket,
    CourseCard,
  },
  data() {
    return {
      coursesData: coursesData,
      selection: [],
    };
  },
  methods: {
    addCourseToSelection(course) {
      this.selection.push(course);
      this.$emit("update-selection", course);
    },
  },
};
</script>

<style></style>
