<template>
    <h1>Упоротая гирлянда. Начало.</h1>
    <ul class="garland">
        <li v-for="garland in garlands" v-bind:key="garland" v-bind:style="`background-color: ${garland}; width:  ${getRandomIntInclusive(150, 220)}px`"
            class="garland__item"></li>
    </ul>
    <span v-html="html"></span>
    <div v-html="otherHtml"></div>

</template>

<script>
export default {
    name: 'App',

    data() {
        return {
            garlands: ['green', 'orange', 'tomato', 'blue', 'red'],
            html: '<span style="color: red">Красный текст</span>',
            otherHtml: '<p style="color: red; width: 100px; height: 300px; outline: 1px solid green;">Красный текст</p>',
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
