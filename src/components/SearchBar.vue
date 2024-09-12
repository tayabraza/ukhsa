<template>
    <form @submit.prevent="onSubmit" class="block w-full">
        <div class="group">
            <input v-model="city" @keyup.enter="handleSearch" placeholder="Enter city name" />
            <button type="button" @click="handleSearch"><i class="fa fa-search"></i> Search</button>
        </div>
    </form>
</template>

<script setup>
import { ref } from 'vue';
const city = ref('');

const emit = defineEmits(['search']);

function handleSearch() {
    if  (city.value.trim() !== '') {
        emit('search', city.value);
    }
}

</script>

<style scoped>

.group{
    display: flex;
    width: 100%;
    height: 40px;
    border-radius: 0.5rem;
    box-shadow: 0px 1px 8px 0.1px #6e6e6e;
}

input, button{
    height: 40px;
    padding: 0.5rem 0rem;
    border-radius: 0.5rem;
    border: none;
    outline: none;
    text-align: center;
    font-size: 1rem;
}
input{
    flex-basis: 400px;
}
button{
    flex-basis: 200px;
    background-color: #00b7ff;
    color: #fff;
    cursor: pointer;
}

@media screen and (min-width: 375px) {
    input{
        flex-basis: 450px;
    }
    button{
        flex-basis: 150px;
    }
}

@media screen and (min-width: 480px) {
    input{
        flex-basis: 480px;
    }
    button{
        flex-basis: 120px;
    }
}

</style>

