<template>
  <div class="wrapper">
    <div class="search-container">
      <h2>Search</h2>
      <input type="text" v-model="filterText" />
    </div>
    <div class="villager-container">
      <div v-bind:key="villager.id" v-for="villager in villagers">
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
  </div>
</template>

<script>
export default {
  name: "VillagerCard",
  props: ["villagers"],
  data() {
    return {
      filterText: ""
    };
  },
  computed: {
    filteredList() {
      let filter = new RegExp(this.filterText, "i"); //regex for capitalization
      return this.villagers.filter(villager => villager.name.match(filter));
    }
  }
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Gamja+Flower&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Inconsolata:wght@400;700&display=swap");

.wrapper {
  max-width: 1200px;
  margin: 0 auto;
  background-repeat: repeat;
}

li {
  text-align: center;
  font-size: 2rem;
}

.villager-name {
  text-transform: uppercase;
  font-size: 3rem;
  background: rgb(235, 255, 236);
  width: 80%;
  margin: 0 auto;
  margin-bottom: 2rem;
  color: rgb(68, 67, 68);
}

.villager-species,
.villager-personality,
.villager-birthday {
  margin-top: 0.5rem;
}

ul {
  padding: 1rem;
  background: #ffffff;
}

.villager-container {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: auto;
  gap: 0.2%;
  background: #ffffff;
}

img {
  width: 200px;
  height: 200px;
  object-fit: contain;
  border-radius: 50%;
  background: #ffffff;
}

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
  border: 2px solid rgb(29, 29, 29);
  padding: 10px;
  margin: 0 auto;
}
</style>
