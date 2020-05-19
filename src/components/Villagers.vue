<template>
  <div class="wrapper">
    <div class="search-container">
      <h2>Search</h2>
      <p>
        Search by
        <span>name</span>,
        <span>species</span>, or
        <span>personality type!</span>
      </p>
      <input type="text" v-model="filterText" />
    </div>
    <div class="villager-container">
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
      return this.villagers.filter(
        villager =>
          villager.name.match(filter) ||
          villager.species.match(filter) ||
          villager.personality.match(filter)
      );
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
  font-size: 2.4rem;
  background: rgba(154, 214, 143, 0.5);
  width: 80%;
  margin: 0 auto;
  margin-bottom: 2rem;
  color: rgb(31, 31, 31);
  padding: 5px 0;
  border-radius: 3px;
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
  color: rgb(31, 31, 31);
  letter-spacing: 10px;
  flex-direction: column;
  text-transform: uppercase;
  display: flex;
  justify-content: center;
  align-items: center;
  background: white;
  padding: 1em 0;
}

input {
  border-radius: 25px;
  border: 2px solid rgb(119, 119, 119);
  padding: 10px;
  margin: 0 auto;
}

p {
  font-size: 1.75rem;
  text-transform: initial;
  letter-spacing: normal;
  margin-bottom: 0.6em;
  color: rgb(31, 31, 31);
  padding-top: 10px;
}

span{
  color: rgb(93, 148, 93);
  font-weight: 900;
}

@media(max-width: 1250px){
  .villager-container {
    grid-template-columns: repeat(3, 1fr);
  }
}

@media(max-width: 950px){
  .villager-container {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media(max-width: 650px){
  .villager-container {
    display: block;
  }

  p{
    width: 60%;
    text-align: center;
    font-size: 1.5rem;
  }

  input{
    width: 50%;
  }

  h2{
    font-size: 2.5rem;
  }
}
</style>
