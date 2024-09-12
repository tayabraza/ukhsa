<template>
    <header>
        <h1 class="title">Airport Terminal Monitoring App</h1>
    </header>
    <main>
        <SearchBar @search="getWeather" />
        <CurrentWeather :weather="weather" />
    </main>
    <footer>
        <p>Copyright &copy; {{ year }}</p>
    </footer>
</template>

<script setup>
import { ref } from 'vue';
import SearchBar from './SearchBar.vue';
import CurrentWeather from './CurrentWeather.vue';

const year = new Date().getFullYear();
const weather = ref(null);

const API_KEY = '357151a9076740db97e222030240909';

async function getWeather(city){
    try {
        const res = await fetch(`https://api.weatherapi.com/v1/forecast.json?key=${API_KEY}&q=${city}&days=1`);
        const data = await res.json();

        weather.value = data;

    } catch (error) {
        console.error(error);
    }
}

</script>