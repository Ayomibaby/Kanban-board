
<template>
    <section class="new-column">
      <div class="inner-wrapper">
      <font-awesome-icon icon="fa-solid fa-circle-plus" />
      <p>Add column</p>
    </div>
    </section>
      </template>
      
      <script >
     import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
import { library } from '@fortawesome/fontawesome-svg-core';
import { faTrash, faCirclePlus } from '@fortawesome/free-solid-svg-icons';

library.add(faTrash, faCirclePlus);
      export default {
        components:{FontAwesomeIcon,},
        name: "addColumn",
        
      }
      </script>
      
      <style scoped>
     .new-column{
      width: 23rem;
  height: 10vh;
  background-color: #161c22;
  border-radius: 20px;
position: relative;
color:white;
padding: 10px;
  /* border: 1px solid #494848; */
     }
       .inner-wrapper{
        display: flex;
        align-items: center;
        column-gap: 10px;
       }
     
      </style>
      