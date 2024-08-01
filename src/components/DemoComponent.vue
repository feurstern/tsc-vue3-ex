<template>
    <h1>This is hte page</h1>
    
</template>

<script lang="ts">
// import { DefineComponent } from 'vue';

interface userDataProps {
    first_name : string;
    last_name : string;
    occupation : string;
    age : number;
}


const userDataArray : userDataProps [] = [
    {
        first_name : 'Hatsune',
        last_name : 'Miku',
        occupation : 'Associate Cybersecurity Analyst',
        age : 17
    },
    {
        first_name : 'Joseph',
        last_name : 'Stalin',
        occupation : 'The Supreme Leader of Uni Soviet',
        age : 45
    },
    {
        first_name : 'Hatsune',
        last_name : 'Miku',
        occupation : 'Fullstack Developer Lead',
        age : 17
    }
]


console.log(userDataArray)

export default({
    props: {
        name : String,
        msg : {type : String, required : true}
    },
    data(){
        return{

        }
    }
})
</script>
