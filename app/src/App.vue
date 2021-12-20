<template>
  <div class="content-container">
    <div class="content">
      <h1>Hearthstone Card Viewer</h1>
      <p class="credit">By Cody Uhi - Dec 20, 2021</p>
      <hr />
      <h2 class="filter-header">Apply Filters:</h2>
      <div class="filters-container flex-row center">
        <div class="filter">
          <p class="filter-label">Class</p>
          <select class="form-control" v-model="this.class">
            <option value="Druid" key="Druid" selected>Druid</option>
            <option value="Warlock" key="Warlock">Warlock</option>
            <option value="NA" key="NA">N/A</option>
          </select>
        </div>
        <div class="filter">
          <p>Mana</p>
          <input type="number" placeholder="Enter Number" v-model="mana" />
        </div>
        <div class="filter">
          <p>Rarity</p>
          <select class="form-control" v-model="rarity">
            <option value="Legendary" key="Legendary" selected>
              Legendary
            </option>
            <option value="NA" key="NA">N/A</option>
          </select>
        </div>
      </div>
      <button @click="getCards()">Search</button>
      <div v-if="isLoading">
        <h2>Loading . . .</h2>
      </div>
      <table class="card-container" v-else>
        <thead>
          <tr>
            <th colspan="2">Image</th>
            <th>Name</th>
            <th>Type</th>
            <th>Rarity</th>
            <th>Set</th>
            <th>Class</th>
          </tr>
        </thead>
        <tbody>
          <Card
            v-for="card in cards"
            :value="card"
            :key="card.name"
            :card="card"
          />
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
import Card from "./components/Card.vue";

export default {
  name: "App",
  data() {
    return {
      isLoading: true,
      class: "Druid",
      mana: 7,
      rarity: "Legendary",
      cards: [],
    };
  },
  components: { Card },
  methods: {
    getCards() {
      try {
        // TODO: Implement network call here
        this.cards = [
          { name: "test", cardTypeId: 4 },
          { name: "test", cardTypeId: 4 },
          { name: "test", cardTypeId: 4 },
          { name: "test", cardTypeId: 4 },
          { name: "test", cardTypeId: 4 },
          { name: "test", cardTypeId: 4 },
          { name: "test", cardTypeId: 4 },
          { name: "test", cardTypeId: 4 },
          { name: "test", cardTypeId: 4 },
        ];
      } catch (err) {
        console.error(err);
      } finally {
        this.isLoading = false;
      }
    },
  },
  mounted() {
    this.getCards();
  },
};
</script>

<style>
* {
  background-color: #1a1c23;
  color: #fff;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}

.content-container {
  margin-top: 30px;
  width: 100%;
  display: flex;
  justify-content: center;
  align-content: center;
}

.content {
  width: 100%;
  max-width: 1080px;
  min-width: 300px;
}

.flex-row {
  display: flex;
  flex-direction: row;
}

.flex-column {
  display: flex;
  flex-direction: column;
}

.center {
  justify-content: center;
  align-items: center;
}

.credit {
  font-size: 12px;
  font-style: italic;
}

hr {
  border: 1px solid lightgray;

}

.filter-header {
  margin-top: 30px;
  padding: 0;
}

.filter-container {
  padding-top: 0;
}

.filter {
  margin: 0 30px 30px 30px;
  padding: 0 10px 10px 10px;
}

.filter > input {
  width: 100px;
}

.filter-label {
  font-size: 15px;
}

.card-container {
  width: 100%;
  margin: 25px 0;
}

table {
  border-collapse: collapse;
}
</style>
