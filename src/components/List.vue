<script setup>
import { ref } from 'vue'
// import WelcomeItem from './WelcomeItem.vue'
// import DocumentationIcon from './icons/IconDocumentation.vue'
// import ToolingIcon from './icons/IconTooling.vue'
// import EcosystemIcon from './icons/IconEcosystem.vue'
// import CommunityIcon from './icons/IconCommunity.vue'
// import SupportIcon from './icons/IconSupport.vue'

// const parentMessage = ref('Parent')
const items = ref([{ message: 'tarefa 1' }, { message: 'tarefa 2' }])
const tarefa = ref('');

const adicionar = () => {
    if (tarefa.value) {
        items.value.push({ message: tarefa.value });
        tarefa.value = ''; // Limpa o campo de entrada
    } else {
        alert('A tarefa nao pode ser vazia');
    }
};

</script>

<template>
    <div class="container">
        <div class="list">
            <li v-for="(item, index) in items">
                <input type="checkbox" name="" id="">
                {{ index }} - {{ item.message }}
            </li>
        </div>
    </div>
    <div class="add">
        <input type="text" v-model="tarefa" placeholder="Escreva aqui">
        <button v-on:click="adicionar">Adicionar</button>
    </div>
</template>


<style scoped>
.container {
    height: fit-content;
    width: 500px;
    background-color: rgb(253, 239, 239);
    margin: 0 auto;
    border-radius: 10px;
    padding: 15px;
    list-style: none;
}
.list{
    color: black;
}
.add{
    display: flex;
    justify-content: center;
    padding: 15px;
}
</style>
