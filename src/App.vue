<template lang="pug">
    div
      transition(name='fade')
        .menu(v-if='menuState')
          ul.menuBox
            li
              a.menuItem(href='#') Empty page
            li
              a.menuItem(href='#') Content
      .header
        // <img @click="toogle" class="burger" src="./assets/burger.svg">
        #navIcon.burger(@click='toogle')
          span
          span
          span
        .logoContain
          img.logo(src='./assets/logo.png')
          span(style='font-size: 30px; margin-left: 10px') Logo
      .mainContain
        .addContain
          button.addButton(@click='openModal')
            span Add Item
        .cardsContain
          item-card.itemCard(v-for='n in 20', :key='n')
        .footer
          span mcldays@gmail.com
      add-item-modal(v-if='modalState', @close='closeModal')
</template>

<script>
import addItemModal from "@/components/addItemModal";
import itemCard from "@/components/itemCard";
export default {
  name: 'App',
  components: {
    itemCard,
    addItemModal
  },
  data(){
    return{
      menuState : false,
      modalState : false
    }
  },
  methods :{
    toogle(){
     document.getElementById('navIcon').classList.toggle('open')
      this.menuState = !this.menuState
    },
    openModal(){
      this.modalState = true
    },
    closeModal(){
      this.modalState = false
    }
  }

}

</script>

<style>
.header{
  height: 70px;
  border-bottom: grey solid 2px;
  display: flex;
  align-items: center;
}
.burger{
  position: absolute;
  z-index: 100;
  padding: 10px;
  margin-left: 10px;
}
.logoContain{
  margin: auto;
  display: flex;
  justify-content: center;
  align-items: center;
}

.logo{
  width: 40px;
  height: 40px;
}

.mainContain{
  height: 70px;
  margin-top: 10px;
}

.addContain{
  display: flex;
  height: 70px;
  justify-content: center;
  align-items: center;
}
.addButton{
  font-size: 15px;
  height: 50px;
  width: 300px;
  border: grey solid 1px;
  background: none;
  cursor: pointer;
}

.addContain :hover{
  background: lightgrey;
  transition: 0.2s linear;
}
.cardsContain{
  display: flex;
  flex-flow: wrap;
  justify-content: center;
}
.itemCard{
  margin-top: 20px;

}
.footer{
  position: sticky;
  bottom: 0;
  background: white;
  margin-top: 5px;
  height: 50px;
  border-top: 1px grey solid;
  display: flex;
  justify-content: end;
  align-items: center;
}
.menuBox{
  display: block;
  position: fixed;
  z-index: 100;
  top: 0;
  width: 300px;
  height: 100%;
  margin: 0;
  padding: 80px 0;
  list-style: none;
  text-align: center;
  background-color: white;
  box-shadow: 1px 0px 6px rgba(0, 0, 0, .10);
}
.menuItem{
  display: block;
  padding: 12px 24px;
  color: #333;
  font-family: 'Roboto', sans-serif;
  font-size: 20px;
  font-weight: 600;
  text-decoration: none;
}
.menuItem:hover{
  background-color: lightgrey;
  transition: 0.2s linear;
}

#navIcon{
  width: 20px;
  height: 10px;
  -webkit-transform: rotate(0deg);
  -moz-transform: rotate(0deg);
  -o-transform: rotate(0deg);
  transform: rotate(0deg);
  -webkit-transition: .5s ease-in-out;
  -moz-transition: .5s ease-in-out;
  -o-transition: .5s ease-in-out;
  transition: .5s ease-in-out;
  cursor: pointer;
}
#navIcon span{
  display: block;
  position: absolute;
  height: 5px;
  width: 100%;
  background: grey;
  border-radius: 9px;
  opacity: 1;
  left: 0;
  -webkit-transform: rotate(0deg);
  -moz-transform: rotate(0deg);
  -o-transform: rotate(0deg);
  transform: rotate(0deg);
  -webkit-transition: .25s ease-in-out;
  -moz-transition: .25s ease-in-out;
  -o-transition: .25s ease-in-out;
  transition: .25s ease-in-out;
}

#navIcon span:nth-child(1) {
  top: 0px;
}

#navIcon span:nth-child(2) {
  top: 10px;
}

#navIcon span:nth-child(3) {
  top: 20px;
}

#navIcon.open span:nth-child(1) {
  top: 10px;
  -webkit-transform: rotate(135deg);
  -moz-transform: rotate(135deg);
  -o-transform: rotate(135deg);
  transform: rotate(135deg);
}

#navIcon.open span:nth-child(2) {
  opacity: 0;
  left: -60px;
}

#navIcon.open span:nth-child(3) {
  top: 10px;
  -webkit-transform: rotate(-135deg);
  -moz-transform: rotate(-135deg);
  -o-transform: rotate(-135deg);
  transform: rotate(-135deg);
}

</style>
