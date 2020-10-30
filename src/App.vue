<template>
  <nav-bar @change-component="updateSelectedComponent"></nav-bar>
  <keep-alive>
    <component
      :is="selectedComponent"
      v-bind="currentProps"
      @update-selection="updateSelection"
    ></component>
  </keep-alive>
</template>

<script>
import NavBar from "./components/navigation/NavBar";
import CourseList from "./components/CourseList";
import SelectedList from "./components/SelectedList";

export default {
  name: "App",
  components: {
    NavBar,
    CourseList,
    SelectedList,
  },
  data() {
    return {
      selectedComponent: "course-list",
      selectionArray: [],
    };
  },
  computed: {
    currentProps() {
      if (this.selectedComponent == "selected-list") {
        return { selection: this.selectionArray };
      }
      return false;
    },
  },
  methods: {
    updateSelectedComponent(comp) {
      this.selectedComponent = comp;
    },
    updateSelection(course) {
      this.selectionArray.push(course);
    },
  },
};
</script>

<style></style>
