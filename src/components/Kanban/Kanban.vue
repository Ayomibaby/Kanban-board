
<template>
<section class="column-wrapper">
<ColumnSections/>
<ColumnSections/>
<ColumnSections/>
</section>
  </template>
  
  <script >
  import ColumnSections from './ColumnSections.vue';
  export default {
    name: "kanBan",
    components:{
        ColumnSections
    }
  }
  </script>
  
  <style scoped>
 .column-wrapper{
    display: flex;
    justify-content: space-between;
 }
  
 /* #ADD8E6 -- light blue */
   
 
  </style>
  