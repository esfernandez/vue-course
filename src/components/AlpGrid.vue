<template>
    <div>
        <table class="alp-table">
        <tr>
            <th>Name</th>
            <th>Lastname</th>
            <th>Age</th>
        </tr>
        <tr v-for="item of dataFront">
            <td>{{item.name}}</td>
            <td>{{item.lastname}}</td>
            <td>{{item.age}}</td>
        </tr>
        </table>
    </div>

    <div>
        <label>Name <input name="txtName" v-model="dataInput.name" type="text" /></label>  
    </div>
    <div>
        <label>Lastname <input v-model="dataInput.lastname" type="text" /></label> 
    </div>
    <div>
        Age <input v-model="dataInput.age" type="number" />
    </div>

    <button type="input" @click="addPerson">Add</button>    

</template>

<script setup>
    import {computed, reactive, onMounted, useSlots} from 'vue';

    const data =[
        {
            name: "Esteban",
            lastname: "Fernandez",
            age: 29,
        },
        {
            name: "Violeta",
            lastname: "Serra",
            age: 31,
        },
        {
            name: "Alexis",
            lastname: "Fernandez",
            age: 20,
        }
    ];

    const dataInput = reactive({
        name: '',
        lastname: '',
        age: ''
    })

    const dataReactive = reactive(data)
    
    const dataFront = computed(() => dataReactive);

    const addPerson = () =>{
        data.push({
            name: dataInput.name,
            lastname: dataInput.lastname,
            age: dataInput.age
        });

        dataInput.name = '';
        dataInput.lastname = '';
        dataInput.age = '';
    }

    const slots = useSlots()

    onMounted(() => {
        console.log(slots.default())
    })

</script>

<style>
.alp-table {
    border: 2px solid;
}

</style>