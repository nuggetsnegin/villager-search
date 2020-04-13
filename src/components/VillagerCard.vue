<template>
  <div class="wrapper">
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
  props: ["villagers"]
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
  background: white;
  border-radius: 25px;
  margin-bottom: 1rem;
  color: rgb(68, 67, 68);
}

.villager-species,
.villager-personality,
.villager-birthday {
  margin-top: 0.5rem;
}

ul {
  padding: 1rem;
  background: rgb(214, 230, 210);
}
.villager-container {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  grid-template-rows: auto;
}

img {
  width: 200px;
  height: 200px;
  object-fit: contain;
  border-radius: 50%;
  background: #ffffff;
}
</style>
