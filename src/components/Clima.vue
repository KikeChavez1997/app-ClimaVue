<script setup>

import useClima from '../composables/useClima'

const { formatearTemperatura} = useClima()


    defineProps({
        clima: {
            type: Object,
            required: true
        }
    })

</script>

<template>
    <div class="resultado">
        <h2>Clima de:{{ clima.name }} </h2>
        <p class="actual">{{ formatearTemperatura(clima.main.temp)  }} &deg;c</p>
        <div class="temperatura">
            <p>Min: {{ formatearTemperatura(clima.main.temp_min) }} <span>&deg;c</span></p>
            <p>Max: {{ formatearTemperatura(clima.main.temp_max) }}<span>&deg;c</span></p>
        </div>

    </div>
</template>
