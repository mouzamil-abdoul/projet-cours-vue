<template>
  <button class="bg-red-900 rounded text-white p-2 absolute right-0 top-0 m-4">
    {{ text }}
  </button>
</template>

<script>
export default {
  name: "base-button",
  props: ["text"],
};
</script>

<style></style>
