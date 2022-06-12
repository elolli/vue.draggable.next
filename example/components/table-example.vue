<template>
  <div class="row">
    <div class="col-8">
      <h3>Draggable table</h3>

      <table class="table table-striped">
        <thead class="thead-dark">
          <tr>
            <th scope="col">Id</th>
            <th scope="col">Name</th>
            <th scope="col">Sport</th>
          </tr>
        </thead>
        <draggable v-model="list" tag="tbody" item-key="name">
          <template #item="{ element }">
            <tr>
              <td scope="row">{{ element.id }}</td>
              <td>{{ element.name }}</td>
              <td>{{ element.sport }}</td>
            </tr>
          </template>
        </draggable>
      </table>
    </div>

    <rawDisplayer class="col-3" :value="list" title="List" />
  </div>
</template>

<script>
import draggable from "@/vuedraggable";
export default {
  name: "table-example",
  display: "Table",
  order: 8,
  components: {
    draggable
  },
  data() {
    return {
      list: [
        { order: 1, name: "Promo1", locations: "loc1, loc2, loc3" },
        { order: 2, name: "Promo2", sport: "loc1, loc2, loc3" },
        { order: 3, name: "Promo3", sport: "loc1, loc2" },
        { order: 4, name: "Promo4", sport: "loc1" }
      ],
      dragging: false
    };
  }
};
</script>
<style scoped>
.buttons {
  margin-top: 35px;
}
</style>
