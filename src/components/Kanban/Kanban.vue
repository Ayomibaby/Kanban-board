<template>
  <section class="column-wrapper">
    <div class="random-testing" v-for="col in columms">
      <ColumnSections
        :data="col"
        :fulldata="columms"
        @deleteColumn="handleDelete"
        @passDelete="taskDelete"
        @clearTasks="handleClear"
      />
    </div>

    <div class="random-testing">
      <addColum :currentcol="columms" />
    </div>
  </section>
</template>

<script>
import ColumnSections from "./ColumnSections.vue";
import addColum from "./addColumn.vue";
export default {
  name: "kanBan",
  components: {
    ColumnSections,
    addColum,
  },
  data() {
    return {
      columms: [
        {
          id: 1,
          tasks: [{ id: 1, taskname: "" }],
          noOFTasks: 0,
          colummsTitle: "",
        },
      ],
    };
  },
  mounted(){
    const sumforeach = (col) =>{
      col.noOFTasks = col.tasks.length
    }
this.columms.forEach(sumforeach)
  },
  methods: {
    handleDelete(id) {
      const colbyid = (col) => {
        return col.id !== id;
      };
      const newcol = this.columms.filter(colbyid);
      this.columms = newcol;

    },

    taskDelete(id, colId) {
      const taskbyid = (task) => {
        return task.id !== id;
      };

      const findfunc = (col) => {
        return col.id == colId
      };
      const findCol = this.columms.find(findfunc);

      const filteredTasks = findCol.tasks.filter(taskbyid);

      findCol.noOFTasks = filteredTasks.length;
  
     findCol.tasks = filteredTasks

    },
    handleClear(colId){
      const findfunc = (col) => {
        return col.id == colId
      };
      const findCol = this.columms.find(findfunc);
      findCol.noOFTasks = 0
      findCol.tasks = []
    }
  },
};
</script>

<style scoped>
.column-wrapper {
  display: flex;

  column-gap: 20px;
  width: 100%;
  overflow-x: auto;
  white-space: nowrap;
}

/* #ADD8E6 -- light blue */
</style>
