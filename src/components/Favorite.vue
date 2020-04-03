<template>
  <div class="wrapper">
    <h1>Villagers</h1>
    <div v-bind:key="villager.id" v-for="villager in villagers">
      <ul class="villager-card">
        <li class="villager-name">{{ villager.name }}</li>
        <li class="villager-image"><img v-bind:src="villager.image" /></li>
        <li class="villager-species">{{ villager.species }}</li>
        <li class="villager-personality">{{ villager.personality }}</li>
        <li class="villager-birthday">{{ villager.birthday }}</li>
      </ul>
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
