<template>
  <tr class="table-row">
    <td colspan="2"></td>
    <td>{{ card.name }}</td>
    <td>{{ card.type ?? "N/A" }}</td>
    <td>{{ card.rarity ?? "N/A" }}</td>
    <td>{{ card.set ?? "N/A" }}</td>
    <td>{{ card.class ?? "N/A" }}</td>
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
  mounted() {
    switch (this.card.cardTypeId) {
      case 4:
        this.cardType = "Minion";
        break;
    }
  },
};
</script>

<style scoped>
.table-row > td {
  border: 1px solid #148eff;
  padding: 15px;
  margin: 0;
}
</style>