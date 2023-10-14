<template>
  <section class="card-wrapper">
    <textarea></textarea>
    <!-- <input type="text"/> -->
  </section>
</template>

<script>
export default {
    name:"task-cards"
}
</script>

<style scoped>
textarea{
    background-color: black;
    height: 110px;
    padding: 10px;
    width: 90%;
    border: none;
    color: white;
    resize: none;
}
textarea:focus{
    outline:none
}
.card-wrapper{
    background-color: black;
    height: 130px;
    border-radius: 10px;
    /* padding: 10px; */
}
</style>
