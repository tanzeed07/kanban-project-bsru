<template>
  <div id="app">
    <Kanban :data="data"/>
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
          tasks:[]
        },
        {
          name: "Doing",
          color: "#16DDFC",
          tasks:[]
        },
        {
          name: "Done",
          color: "#FE0D0D",
          tasks:[]
        },
      ],
    };
  },
};
</script>

<style>
#app {
  height: 100vh;
}
</style>
