<template>
  <div class="home">
    <ListItem itemName="My item1" />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import ListItem from "@/components/ListItem.vue";

export default {
  name: "Home",
  components: {
    ListItem
  }
};
</script>
