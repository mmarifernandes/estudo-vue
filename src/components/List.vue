<script setup>
import { ref } from 'vue'

const items = ref([])
const tarefa = ref('');

const adicionar = () => {
    if (tarefa.value) {
        items.value.push({ descricao: tarefa.value, checked: false });
        tarefa.value = ''; // Limpa o campo de entrada
    } else {
        alert('A tarefa nao pode ser vazia');
    }
};

</script>

<template>

    <div class="add">
        <textarea v-model="tarefa" placeholder="Escreva aqui"> </textarea>
        <button v-on:click="adicionar">Adicionar</button>
    </div>

    <div class="container">
        <div class="list">
            <li v-if="items.length > 0" v-for="(item, index) in items" class="" :class="{ done: item.checked }">
                <p> <input type="checkbox" v-model="item.checked" :id="'checkbox-' + index">
               {{ item.descricao }}</p>
            </li>
            <li v-else class="vazio"> Vazio.. </li>
        </div>
    </div>
    
</template>


<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,300..800;1,300..800&family=Patrick+Hand&display=swap');

.container {
    height: fit-content;
    width: 500px;
    background-color: rgb(253, 239, 239);
    margin: 0 auto;
    border-radius: 10px;
    padding: 15px;
    list-style: none;
    line-break: anywhere;
    
}
.list{
    color: rgb(79, 79, 79);
}
input[type="checkbox"] {
    margin-right: 10px;
}
p{
    display: flex;
    align-items: baseline;
    line-height: 18px;
    font-family: "Open Sans", sans-serif;
    font-weight: 400;
    font-style: normal;
    /* font-size: 1.2rem; */

}
.add textarea{
    height: 50px;
    width: 420px;
    border-radius: 10px;
    padding: 10px;
    border: 3px solid rgb(253, 239, 239);
    resize: none;
    font-family: "Open Sans", sans-serif;
    font-weight: 400;
    font-style: normal;
    /* font-size: 1rem; */
}
.add{
    display: flex;
    /* justify-content: center; */
    padding-bottom: 15px;
    justify-content: space-between;
}
.done {
    text-decoration: line-through;
    color: gray;
    background-color: rgb(247, 232, 232);
    border-radius: 10px;
}
.vazio{
    color: gray;
}
li{
    padding: 8px;
}
li:hover{
    background-color: rgb(245, 226, 226);
    border-radius: 10px;
    

}
button{
    border-radius: 10px;
    background-color: white;
    border: 3px solid rgb(253, 239, 239);
    font-family: "Open Sans", sans-serif;
    font-weight: 400;
    font-style: normal;
    cursor: pointer;
    /* font-size: 1rem; */
}
</style>
