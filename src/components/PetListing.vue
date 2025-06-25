<script setup>
import {defineProps} from 'vue';
import {onMounted, ref} from 'vue';

const pets = ref ([]);


onMounted(async () =>{
    try{
        const response = await fetch ('');
        if (!response.ok){
            throw new Error("Network reponse error");
        }
        const data = await response.json();

    }catch (error){
        console.error('Fetching error', error);
    }
    console.log ('Pets fetched', pets.value.length, 'Addoptions')
});


const props = defineProps({
    title:{
        type:String,
        default:'Pet Listings'
    }
})
</script>
<template>
    <div class = "container">
        <h2 id="petlisting_title">{{ props.title }}</h2>
    <div id="flex_col">
        <div id="flex_row">
            <div class="animals"></div>
            <div class="animals"></div>

        </div>
        <div id="flex_row">
            <div class="animals"></div>
            <div class="animals"></div>

        </div>
        </div>
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

}
#petlisting_title {
    text-align: center;
    font-family: 'square';
    font-weight: bold;
}

#top_bar {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 60px;
  background-color: rgb(148, 208, 246);
  color: rgb(68, 55, 79);
  font-family: 'cake';
  font-size: 2rem;
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
  font-size: 2rem;
  text-align: center;
  padding: 10px;
  width: 300px;
  min-height: 270px;
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
