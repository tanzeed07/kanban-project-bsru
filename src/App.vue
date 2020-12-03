<template>
  <div id="app">
    <Kanban
      :data="data"
      :create_task_submit="create_task_submit"
      :move_item_task="move_item_task"
    />
  </div>
</template>

<script>
import Kanban from "./components/Kanban";

export default {
  name: "App",
  components: {
    Kanban,
  },
  data() {
    return {
      data: [
        {
          name: "To do",
          color: "#1E8449",
          tasks: [
            {
              task_name: "test",
            },
          ],
        },
        {
          name: "Doing",
          color: "#0946F7",
          tasks: [
            {
              task_name: "test",
            },
          ],
        },
        {
          name: "Done",
          color: "#FE0D0D",
          tasks: [
            {
              task_name: "test",
            },
          ],
        },
      ],
    };
  },
  methods: {
    create_task_submit(column_index, item) {
      this.data[column_index].tasks.push(item);
    },
    move_item_task(column_a, index_task_a, column_b, index_task_b) {
      var item = this.data[column_a].tasks[index_task_a];
      // remove task before
      this.data[column_a].tasks.splice(index_task_a, 1);
      // move to
      this.data[column_b].tasks.splice(index_task_b, 0, item);
    },
  },
};
</script>

<style>
#app {
  height: 100vh;
}
</style>
