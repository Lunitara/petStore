<script setup>
import { ref } from "vue";
import AdoptionApplication from './components/AdoptionApplication.vue';
import PetListing from './components/PetListing.vue';

let activePage = ref('home');
function navigateTo(page) {
  activePage.value = page;
  console.log(page);
}
const pet_pictures = ["petpictures\fish.jpg", "petpictures\gold.jpg", "petpictures\king.jpg", "petpictures\sam.jpg"]

function add_picture () {
  for (pic in pet_pictures) {
    animals.style.backgroundImage = pic
  }
}
const show_pets = false
</script>

<template>
  <div id="top_bar">
    <h1>Sebastian Adoptions</h1>
    <nav>
      <p id="home_word"
      @click="navigateTo('home')">HOME</p>
    </nav>
  </div>

  <div id="wrapper">
    <div id="heroFlex">
      <div class="middiv">
        ADOPT<br>
        A<br>
        FRIEND<br>
        TODAY<br>
        <button id="adopt" @click="navigateTo('AdoptionApplication')">Create An Adoption</button>
      </div>
      <img id="paws" src="/pawprint.jpg" width="404px">
    </div>
    <button id="see_listing"
    @click="navigateTo('PetListing')">See All Listings</button>
    
    <PetListing  v-if="activePage === 'PetListing'"/>
  </div>
</template>

<style>
html, body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  width: 100%;
  height: 100%;
}
*, *::before, *::after {
  box-sizing: inherit;
}
</style>

<style scoped>
@font-face {
  font-family: 'cake';
  src: url('Eracake.ttf');
}
@font-face {
  font-family: 'square';
  src: url('square.ttf');
}

h1, #paws {
  margin: 0;
  padding: 0;
}

#wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 100%;
  padding-bottom: 100px;
}

#top_bar {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 60px;
  background-color: rgb(148, 208, 246);
  color: rgb(68, 55, 79);
  font-family: 'cake';
  font-size: 1.5rem;
}

#home_word {
  position: absolute;
  left: 8px;
  top: 0px;
  font-family: 'square';
  font-weight: bold;
  cursor: pointer;
}


#heroFlex {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  width: 100%;
}

.middiv {
  background-color: #c6e9ff;
  font-family: 'square';
  font-weight: bold;
  font-size: 2rem;
  text-align: center;
  padding: 10px;
  width: 300px;
  min-height: 270px;
}
#see_listing {
  color: rgb(19, 17, 17);
  background-color: rgb(254, 253, 255);
  border-radius: 20px;
  font-size: 1.2rem;
  border: 2px solid rgb(23, 22, 22);
  cursor: pointer;
  margin-top: 10px;
}
#adopt {
  color: white;
  background-color: rgb(68, 55, 79);
  border-radius: 20px;
  font-size: 1.2rem;
  border: 4px solid white;
  cursor: pointer;
  margin-top: 10px;
}

#flex_col {
  display: flex;
  flex-direction: column;
  align-items: center;
}

#flex_row {
  display: flex;
  justify-content: center;
  gap: 20px;
  flex-wrap: wrap;
  margin: 10px 0;
}

.animals {
  background-color: white;
  height: 200px;
  width: 300px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  flex-shrink: 0;
}

@media screen and (max-width: 900px) {
  .animals {
    width: 300px;
  }
}
</style>
