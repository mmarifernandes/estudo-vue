<script setup>
import { ref } from 'vue'
// import WelcomeItem from './WelcomeItem.vue'
// import DocumentationIcon from './icons/IconDocumentation.vue'
// import ToolingIcon from './icons/IconTooling.vue'
// import EcosystemIcon from './icons/IconEcosystem.vue'
// import CommunityIcon from './icons/IconCommunity.vue'
// import SupportIcon from './icons/IconSupport.vue'

const parentMessage = ref('Parent')
const items = ref([{ message: 'Foo' }, { message: 'Bar' }])
</script>

<template>
    <div class="container">
        <div class="list">
            <li v-for="(item, index) in items">
                {{ parentMessage }} - {{ index }} - {{ item.message }}
            </li>
        </div>
    </div>

</template>


<style scoped>
.container {
    height: 200px;
    width: 50vw;
    background-color: rgb(253, 239, 239);
    margin: 0 auto;
    border-radius: 10px;
    padding: 15px;
    list-style: none;
}
.list{
    color: black;

}
</style>
