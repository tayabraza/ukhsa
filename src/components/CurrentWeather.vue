<template>
    <div v-if="weather?.location && weather?.current">
        <div class="weather-card" :class="[Number(weather.location.localtime.slice(10,13)) > 6 && Number(weather.location.localtime.slice(10,12)) < 20 ? 'day' : 'night']">
            <h3>{{ weather.location.name }}, {{ weather.location.region }}, {{ weather.location.country }}</h3>
            <h2>{{ Math.floor(weather.current.temp_c) }}°C</h2>
            <img :src="weather.current.condition.icon" :alt="weather.current.condition.text">
            <h4>Time: {{ weather.location.localtime.slice(10) }}</h4>
        </div>
    </div>
    <div v-if="weather?.error">
        <h1>City not found.</h1>
    </div>
</template>

<script setup>
const props = defineProps({
    weather: Object,
});
</script>