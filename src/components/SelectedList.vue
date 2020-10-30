<template>
  <div class="container w-4/5 mx-auto mt-4">
    <h1 class="text-lg font-bold">Mes cours</h1>
    <div v-if="selection.length == 0">
      <p>Vous n'avez choisi aucun cours pour le moment</p>
    </div>
    <div v-else>
      <selected-card
        v-for="course in selection"
        :key="course.name"
        :course="course"
      ></selected-card>
    </div>
  </div>
</template>

<script>
import SelectedCard from "./SelectedCard";
export default {
  name: "selected-list",
  components: {
    SelectedCard,
  },
  props: ["selection"],
};
</script>

<style></style>
