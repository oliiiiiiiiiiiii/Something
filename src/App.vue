<template>
  <div class="container">
    <Header title="Some Text Below" />
    <Tasks @delete-task="deleteTask" :tasks="tasks" />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Tasks from "./components/Tasks.vue";
export default {
  name: "App",
  components: {
    Header,
    Tasks,
  },
  data() {
    return {
      tasks: [],
    };
  },
  methods:{
    deleteTask(id){
      if (confirm("Are you sure ?")){
        this.tasks = this.tasks.filter((task) =>  task.id !== id)
    }
    }
  },
  created() {
    this.tasks = [
      {
        id: 1,
        text: "Geno retired",
        day: "someday",
        reminder: true,
      },
      {
        id: 2,
        text: "as head mod",
        day: "someday2",
        reminder: true,
      },
      {
        id: 3,
        text: "To get most active role",
        day: "someday3",
        reminder: false,
      },
    ];
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap");
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: "Poppins", sans-serif;
  background-color: rgb(255, 255, 255);
}
.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 2px solid rgb(0, 0, 0);
  padding: 30px;
  border-radius: 50px;
  background: rgb(255, 255, 255);
  color: rgb(0, 0, 0);
}
</style>
