<template>
  <tr class="table-row">
    <td colspan="2">
      <img :src="card.image" :alt="card.name" />
    </td>
    <td>{{ card.name ?? "N/A" }}</td>
    <td>{{ card.cardTypeId ? getType(card.cardTypeId) : "N/A" }}</td>
    <td>{{ card.rarityId ? getRarity(card.rarityId) : "N/A" }}</td>
    <td>{{ card.cardSetId ? getSet(card.cardSetId) : "N/A" }}</td>
    <td>{{ card.classId ? getClass(card.classId) : "N/A" }}</td>
  </tr>
</template>

<script>
export default {
  name: "Card",
  props: {
    card: Object,
  },
  data() {
    return {
      cardType: undefined,
    };
  },
  methods: {
    //   ALTERNATIVE WAY OF "GETTING" EVERYTHING:
    //      Instead of statically looking up ID values here, cache these values somewhere and reference that cache
    //      Update the cache regularly on an automated schedule so there's no manual upkeep
    getType(id) {
      switch (id) {
        case 3:
          return "Hero";
        case 4:
          return "Minion";
        case 5:
          return "Spell";
        case 7:
          return "Weapon";
        case 8:
          return "Hero Power";
      }
    },
    getRarity(id) {
      switch (id) {
        case 1:
          return "Common";
        case 2:
          return "Free";
        case 3:
          return "Rare";
        case 4:
          return "Epic";
        case 5:
          return "Legendary";
      }
    },
    getSet(id) {
      switch (id) {
        case 1637:
          return "Core";
        case 1635:
        case 3:
        case 4:
          return "Legacy";
        case 1626:
          return "Fractured in Alterac Valley";
        case 1578:
          return "United in Stormwind";
        case 1525:
          return "Forged in the Barrens";
        case 1646:
          return "Classic Cards";
        case 1466:
          return "Madness at the Darmoon Faire";
        case 1443:
          return "Scholomance Academy";
        case 1463:
          return "Demon Hunter Initiate";
        case 1414:
          return "Ashes of Outland";
        case 1403:
          return "Galakrond's Awakening";
        case 1347:
          return "Descent of Dragons";
        case 1158:
          return "Saviors of Uldum";
        case 1130:
          return "Rise of Shadows";
        case 1129:
          return "Rastakhan's Rumble";
        case 1127:
          return "The Boomsday Project";
        case 1125:
          return "The Witchwood";
        case 1004:
          return "Kobolds and Catacombs";
        case 1001:
          return "Knights of the Frozen Throne";
        case 27:
          return "Journey to Un'Goro";
        case 25:
          return "Mean Streets of Gadgetzan";
        case 23:
          return "One Night in Karazhan";
        case 21:
          return "Whispers of the Old Gods";
        case 20:
          return "League of Explorers";
        case 15:
          return "The Grand Tournament";
        case 14:
          return "Blackrock Mountain";
        case 13:
          return "Goblins vs Gnomes";
        case 12:
          return "Curse of Naxxramas";
      }
    },
    getClass(id) {
      switch (id) {
        case 2:
          return "Druid";
        case 3:
          return "Hunter";
        case 4:
          return "Mage";
        case 5:
          return "Paladin";
        case 6:
          return "Priest";
        case 7:
          return "Rogue";
        case 8:
          return "Shaman";
        case 9:
          return "Warlock";
        case 10:
          return "Warrior";
        case 12:
          return "Neutral";
        case 14:
          return "Demon Hunter";
      }
      return "N/A";
    },
  },
};
</script>

<style scoped>
.table-row > td {
  border: 1px solid #148eff;
  padding: 15px;
  margin: 0;
}

img {
  width: 250px;
}
</style>