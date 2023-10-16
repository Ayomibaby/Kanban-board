
<template>
<section class="column-wrapper">

  <div class="random-testing" v-for="col in columms">
<ColumnSections :data="col"/>
</div>

<div class="random-testing" >
<addColum :currentcol="columms"/>
</div>


</section>
  </template>
  
  <script >
  import ColumnSections from './ColumnSections.vue';
  import addColum from './addColumn.vue'
  export default {
    name: "kanBan",
    components:{
        ColumnSections,
        addColum
    }, 
    data(){
      return{
        columms:[
          {
           id:1,
            tasks:[],
            noOFTasks:0,
            colummsTitle:'',
        }
      ]
      }
    }, 
    watch:{
      columms(newcols, oldcols){
        console.log(this.columms)
       console.log(newcols)
      }
    }, 
    // mounted(){
    //   console.log(this.columms)
    // }
  }
  </script>
  
  <style scoped>
 .column-wrapper{
    display: flex;
   
    column-gap: 20px;
    width: 100%;
    overflow-x: auto;
    white-space: nowrap
 }
  

 /* #ADD8E6 -- light blue */
   
 
  </style>
  