<template lang="pug">
  .modalMask
    .modalWrapper
      .modalContainer
        .modalHeader
          span Create new Item
        .modalBody
          .inputContain
            span.placeholder Name:
            input(style='height: 20px')
          .inputContain
            span.placeholder Image:
            input(type='file')
          .inputContain
            span.placeholder Description:
            textarea
          .inputContain.checkbox
            input#check.customCheckbox(type='checkbox' name='check' value='yes')
            label(for='check') Show
        .footerModal
          button.buttonFooter OK
          button.buttonFooter(@click="$emit('close')") Close
</template>

<script>
export default {
  name: "addItemModal"
}
</script>

<style scoped>
.modalMask {
  position: fixed;
  z-index: 9998;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: table;
  transition: opacity 0.3s ease;
}
.modalWrapper {
  display: table-cell;
  vertical-align: middle;
}

.modalHeader{
  text-align: center;
  padding: 10px;
  border-bottom: 1px solid grey;
}

.placeholder{
  padding: 2px;
  font-size: 15px;
}
.inputContain {
  display: flex;
  flex-direction: column;
  margin-top: 20px;
}

.checkbox{
  align-items: start;
  display: block;
  justify-content: center;
}

.modalContainer {
  width: 300px;
  margin: 0px auto;
  font-size: 20px;

  background-color: #fff;
  border-radius: 2px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.33);
  transition: all 0.3s ease;
  font-family: Helvetica, Arial, sans-serif;
}


.modalBody {
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 0px 20px 20px 20px;
}

.footerModal{

  padding-bottom: 20px;
  display: flex;
  justify-content: space-around;
}

.buttonFooter{
  width: 110px;
  height: 30px;
}

.customCheckbox{
  position: absolute;
  z-index: -1;
  opacity: 0;
}

.customCheckbox+label {
  display: inline-flex;
  align-items: center;
  user-select: none;
}
.customCheckbox+label::before {
  content: '';
  display: inline-block;
  width: 1em;
  height: 1em;
  flex-shrink: 0;
  flex-grow: 0;

  margin-right: 0.5em;
  background-image: url("../assets/checkbox-default.svg");
}

.customCheckbox:checked+label::before {
  background-image: url("../assets/checkbox-active.svg");
}

.modalDefaultButton {
  float: right;
}

</style>