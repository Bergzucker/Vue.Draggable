<template>
  <draggable 
    :multiDrag="true" 
    class="dragArea" 
    tag="ul" 
    :list="tasks" 
    @select="onSelect"
    @deselect="onDeSelect"
    :group="{ name: 'g1' }">
    <li v-for="el in tasks" :key="el.name">
      <p>{{ el.name }}</p>
      <nested-draggable :tasks="el.tasks" />
    </li>
  </draggable>
</template>
<script>
import draggable from "@/vuedraggable";

export default {
  props: {
    tasks: {
      required: true,
      type: Array
    }
  },
  components: {
    draggable
  },
  name: "nested-draggable",
  methods: {
    onSelect(data) {
      debugger
    },
    onDeSelect(data) {
      debugger
    }
  }
};
</script>
<style scoped>
.dragArea {
  min-height: 50px;
  outline: 1px dashed;
}
</style>

<style>
.sortable-selected {
  background-color: green;
}
</style>
