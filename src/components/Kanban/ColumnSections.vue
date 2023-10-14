<template>
  <section class="columnWrapper">
    <div>
      <div class="title">
        <div class="title-identity">
          <h2>0</h2>
          <input type="text" class="name-input" placeholder="Name" />
        </div>
        <div class="delete">Delete</div>
      </div>
    </div>
    <div class="cards">
        <taskCards/>
    </div>
    <div class="outer-task">
    <div class="tasks">
      <input type="text" placeholder="add Task" class="name-input" />
      <p>clear</p>
    </div>
</div>
  </section>
</template>

<script>
import taskCards from './taskCards.vue';
export default {
    components:{taskCards},
  name: "ColumnSections",
};
</script>

<style scoped>
.columnWrapper {
  width: 30%;
  height: 90vh;
  background-color: #161c22;
  border-radius: 20px;
position: relative;
color:white;
padding: 10px;
  /* border: 1px solid #494848; */
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
  width: 80%;
}
.delete {
  width: 20%;
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
.outer-task{
    position: absolute;
     bottom:0;
     background: #000;
     border-radius: 10px;
     width: 95%;
     margin: 10px auto;
}
.tasks{
    display: flex ;
   
    /* justify-content: space-between;   */
      align-items: center;
     column-gap: 30px;
     padding: 10px;
    
     
}
</style>
