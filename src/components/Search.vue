<template>
  <div class="search-container">
    <label>Search Villager</label>
    <input type="text" v-model="search" />
    <!-- <div v-bind:key="villagers.name" v-for="villagers in filteredList"></div> -->
  </div>
</template>

<script>
export default {
  name: "search-container",
  props: ["villagers"],
  computed: {
    filteredList() {
      return this.villagers.filter(villagers => {
        return villagers.name.toLowerCase().includes(this.search.toLowerCase());
      });
    }
  }
};
</script>

<style scoped>
.search-container {
  font-size: 3rem;
  letter-spacing: 10px;
  flex-direction: column;
  text-transform: uppercase;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 2rem;
  margin-bottom: 1rem;
}

input {
  border-radius: 25px;
  border: 2px solid rgb(63, 63, 63);
  padding: 10px;
}
</style>
