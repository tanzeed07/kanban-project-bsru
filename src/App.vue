<template>
  <div id="app">
    <Kanban :data="data" :create_task_submit="create_task_submit"/>
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
          tasks:[{
            task_name: "test"
          },
          ],
        },
        {
          name: "Doing",
          color: "#16DDFC",
          tasks:[{
            task_name: "test"
          },
          ],
        },
        {
          name: "Done",
          color: "#FE0D0D",
          tasks:[{
            task_name: "test"
          },
          ],
        },
      ],
    };
  },
  methods:{
    create_task_submit(column_index, item){
     this.data[column_index].tasks.push(item)
    }
  }
};
</script>

<style>
#app {
  height: 100vh;
}
</style>
