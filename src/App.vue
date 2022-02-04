<template>
    <h1>Упоротая гирлянда. Начало.</h1>

    <div class="buttons">
        <button v-on:click="garland = !garland" type="button">гирлянды</button>
        <button v-on:click="peak = !peak" type="button">пики точеные</button>
        <button v-on:click="march = !march" type="button">8 марта</button>
    </div>


    <section>
        <h2>Вот что ты выбрал (-о)</h2>
        <ul class="garland" v-if="garland">
            <li v-for="garland in garlands" v-bind:key="garland" v-bind:style="`background-color: ${garland}; width:  ${getRandomIntInclusive(150, 220)}px`"
                class="garland__item"></li>
        </ul>

        <div class="picture peak" v-if="peak"></div>


        <div class="picture march" v-if="march"></div>


    </section>

</template>

<script>
export default {
    name: 'App',

    data() {
        return {
            garland: false,
            peak: false,
            march: false,
            garlands: ['green', 'orange', 'tomato', 'blue', 'red'],
        }
    },

    methods: {
        getRandomIntInclusive(min, max) {
            min = Math.ceil(min);
            max = Math.floor(max);
            return Math.floor(Math.random() * (max - min + 1)) + min; //Максимум и минимум включаются
        }
    },
}
</script>

<style src="./assets/style.css">
</style>
