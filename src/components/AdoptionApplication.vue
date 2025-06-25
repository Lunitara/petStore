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
        default:'Adoption Application'
    }
})
</script>
<template>
    <div class = "container">
        <h2>{{ props.title }}</h2>

    </div>
    
</template>