<template lang="pug">
      .main
        .cardContain
          span Item Name
          .card
          span.description
            | Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ab amet at culpa, distinctio dolores doloribus, eligendi error, illum nisi odit provident quod quos reiciendis! Ab fugit officia quaerat quod totam.
</template>

<script>
export default {
  name: "itemCard"
}
</script>

<style scoped>
.card{
  margin-top: 5px;
  width: 300px;
  height: 150px;
  border: black 1px solid;
  box-shadow: 2px 2px 10px rgba(0, 0, 0, .5);
}
.cardContain{
  width: 300px;
  height: 100%;
  margin-inline: 50px;
  text-align: center;
  font-size: 20px;
}
.description{
  font-size: 10px;
  word-wrap: break-word; /* old name */
  overflow-wrap: break-word;
}

</style>