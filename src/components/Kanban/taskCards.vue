<template>
  <section class="card-wrapper">
    <textarea placeholder="Enter Task"></textarea>
    <div class="delete">
    <font-awesome-icon icon="fa-solid fa-trash" /> 
  </div>
  </section>
</template>

<script>

import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
import { library } from '@fortawesome/fontawesome-svg-core';
import { faTrash } from '@fortawesome/free-solid-svg-icons';

library.add(faTrash);
export default {
  components:{FontAwesomeIcon},
    name:"task-cards"
}
</script>

<style scoped>
textarea{
    background-color: black;
    height: 110px;
    font-size: 16px;
    width: 90%;
    border: none;
    color: white;
    resize: none;
}
textarea:focus{
    outline:none
}
textarea::placeholder{
  font-size: 16px;
}
.card-wrapper{
    background-color: black;
    height: 130px;
    border-radius: 10px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 10px;
}
.delete{
 width: 10%;
}
</style>
