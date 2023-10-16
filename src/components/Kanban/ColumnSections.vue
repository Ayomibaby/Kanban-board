<template>
  <section class="content-wrap" v-on:ondrop="drop" v-on:dragover="allowDrop">
    <div>
      <div class="title">
        <div class="title-identity">
          <h4>{{ data.noOFTasks }}</h4>
          <input type="text" class="name-input" placeholder="Name" />
        </div>
        <div class="delete" @click="deleteColumn">
          <font-awesome-icon icon="fa-solid fa-trash" />
        </div>
      </div>
    </div>
    <div class="cards">
      <taskCards v-for="ta in data.tasks" :details="ta" @deleteTask="passDelete" />
    </div>
    <div class="outer-task">
      <div class="tasks">
        <div class="add-btn" @click="addtask">
          <font-awesome-icon icon="fa-solid fa-circle-plus" />
          <h3>Add task</h3>
        </div>
        <p @click="clearTasks">clear</p>
      </div>
    </div>
  </section>
</template>

<script>
import taskCards from "./taskCards.vue";
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import { library } from "@fortawesome/fontawesome-svg-core";
import { faTrash, faCirclePlus } from "@fortawesome/free-solid-svg-icons";

library.add(faTrash, faCirclePlus);

export default {
  props: ["data", "fulldata"],
  components: { taskCards, FontAwesomeIcon },
  name: "ColumnSections",
  methods: {
    allowDrop(ev) {
      ev.preventDefault();
    },
    drop(ev) {
      ev.preventDefault();
      var data = ev.dataTransfer.getData("text");
      ev.target.appendChild(document.getElementById(data));
    },
    deleteColumn() {
      const id = this.data.id;
      this.$emit("deleteColumn", id);
    },
    addtask() {
      const taskid = this.data.tasks.length + 1;
      this.data.tasks.push({id: taskid, taskname:""})
      this.data.noOFTasks = this.data.tasks.length
    },
    passDelete(id){
      const colId = this.data.id
     this.$emit("passDelete", id, colId) 
    }, 
    clearTasks(){
      const colId = this.data.id
      this.$emit("clearTasks", colId)
    }
  },
};
</script>

<style scoped>
.content-wrap {
  width: 23rem;
  height: 90vh;
  background-color: #161c22;
  border-radius: 20px;
  position: relative;
  color: white;
  padding: 10px;
  /* border: 1px solid #494848; */
}
.cards {
  overflow-y: scroll;
  height: 60vh;
}
.title {
  display: flex;
  justify-content: space-between;
  background-color: black;
  align-items: center;
  border-radius: 10px;
  margin-bottom: 10px;
}
.title-identity {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 90%;
}
.delete {
  width: 10%;
}
.delete,
.title {
  padding: 0 10px;
}

.name-input {
  width: 90%;
  height: 50px;
  border: none;
  font-size: 18px;
  font-weight: 600;
  color: white;
  background: black;
}
.name-input:focus {
  outline: none;
}

.name-input::placeholder {
  font-size: 18px;
  font-weight: 600;
  color: white;
}
.outer-task {
  position: absolute;
  bottom: 0;
  background: #000;
  border-radius: 10px;
  width: 95%;
  margin: 10px auto;
}
.tasks {
  display: flex;

  justify-content: space-between;
  align-items: center;
  /* column-gap: 30px; */
  padding: 10px;
}
.add-btn {
  display: flex;
  column-gap: 10px;
  align-items: center;
}
</style>
