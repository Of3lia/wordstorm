<script setup lang="ts">
import { ref } from "vue";
import * as _words from "../assets/words.json"

const words: any = _words.words
// const numberOfWords = ref(3)
const result = ref<string[]>([])

function generate() {
  let num = randNumb()
  result.value.push(words[num])
  console.log(num)
}

const randNumb = () => Math.floor(Math.random() * (words.length - 0 + 1) + 0)

// function randomIntFromInterval(min, max) { // min and max included 
//   return Math.floor(Math.random() * (max - min + 1) + min)
// }

</script>

<template>
  <main>
    <div>Total ammount of words: {{ words.length }}</div>
    <!-- <label for="numberOfWords">Number of words</label>
    <input id="numberOfWords" type="number" v-model="numberOfWords"> -->
    <button @click="generate">Get a random Word</button>
    <br />
    <h3>Result:</h3>
    <hr />
    <label v-for="word in result">{{ word }} &nbsp;</label>
  </main>
</template>
