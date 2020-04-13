<template>
  <div class="search-container">
    <label>Search Villager</label>
    <input type="text" v-model="search" />
    <div v-bind:key="villager.id" v-for="villager in filteredList">
      <ul class="villager-card">
        <li class="villager-name">{{ villager.name }}</li>
        <li class="villager-image">
          <img v-bind:src="villager.image" />
        </li>
        <li class="villager-species">{{ villager.species }}</li>
        <li class="villager-personality">{{ villager.personality }}</li>
        <li class="villager-birthday">{{ villager.birthday }}</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "search-container",
  props: ["villagers"],
  computed: {
    filteredList() {
      return this.villagers.filter(villager => {
        return villager.name.toLowerCase().includes(this.search.toLowerCase());
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
