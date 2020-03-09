<template>
  <div>
    <div class="form-group">
      <input
        @keydown.enter="addNote()"
        type="text"
        v-model="input"
        placeholder="Enter TODO item"
        class="form-control"
      />
    </div>
    <ul class="list-group">
      <p v-if="!items.length">Add an item to begin.</p>
      <li @click="hide(item)" v-for="item in items" class="list-group-item" :key="item">{{ item }}</li>
    </ul>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "ListItem",
  data() {
    return {
      input: "",
      items: ["to do item 1", "to do item 2"]
    };
  },
  methods: {
    hide(itemText: string): void {
      this.items = this.items.filter(item => {
        return item !== itemText;
      });
    },
    addNote(): void {
      if (!this.input) return;
      this.items.push(this.input);
      this.input = "";
    }
  }
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.listItem {
  width: 200px;
  height: 1em;
}
p {
  color: red;
}
</style>
