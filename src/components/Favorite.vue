<template>
  <div class="wrapper">
    <h1>Villagers</h1>
    <div v-bind:key="villager.id" v-for="villager in villagers">
      <h3>{{ villager.name }}</h3>
    </div>
  </div>
</template>

<script>
export default {
  name: "Favorite",
  props: ["villagers"]
};
</script>

<style scoped></style>
