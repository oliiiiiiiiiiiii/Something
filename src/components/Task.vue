<template>
    <div :class="[task.reminder ? 'reminder' : 'noreminder', 'task']">
        <h3>
            {{task.text}}
            <i @click="onDelete(task.id)" class="fas fa-times"></i>
        </h3>
        <p>{{task.day}}</p>
    </div>
</template>

<script>
export default {
    name:'Task',
    props:{
        task:Object
    },
    methods:{
        onDelete(id){
            this.$emit('delete-task',id)
        }
    }
}
</script>


<style scope>
.fas {
  color: red;
}
.task {
  background: #ffffff;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
  color: rgb(0, 0, 0);
  border-right: 5px solid rgb(0, 0, 0);
  border-top: 5px solid rgb(0, 0, 0);
  border-bottom: 5px solid rgb(0, 0, 0);
}
.task.reminder {
  border-left: 5px solid rgb(0, 255, 0);
}
.task.noreminder {
  border-left: 5px solid rgb(255, 0, 0);
}
.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>