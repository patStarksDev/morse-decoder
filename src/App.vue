<!-- <script setup>
import { RouterLink, RouterView } from 'vue-router'
</script> -->

<template>
  <h1>-- --- .-. ... .. -.   .- .-. --- ..- -. -..</h1>
  <h1>morsin around</h1>
  <input v-model="encoder" placeholder="enter text to encode">
  <p>{{ encode() }}</p>
  <input v-model="decoder" placeholder="enter morse to decode">
  <p>{{ decode() }}</p>
</template>

<script setup>
import { ref } from 'vue'
const encoder = ref('')
const decoder = ref('')

const abc = {
  "0": "-----",
  "1": ".----",
  "2": "..---",
  "3": "...--",
  "4": "....-",
  "5": ".....",
  "6": "-....",
  "7": "--...",
  "8": "---..",
  "9": "----.",
  "a": ".-",
  "b": "-...",
  "c": "-.-.",
  "d": "-..",
  "e": ".",
  "f": "..-.",
  "g": "--.",
  "h": "....",
  "i": "..",
  "j": ".---",
  "k": "-.-",
  "l": ".-..",
  "m": "--",
  "n": "-.",
  "o": "---",
  "p": ".--.",
  "q": "--.-",
  "r": ".-.",
  "s": "...",
  "t": "-",
  "u": "..-",
  "v": "...-",
  "w": ".--",
  "x": "-..-",
  "y": "-.--",
  "z": "--..",
  ".": ".-.-.-",
  ",": "--..--",
  "?": "..--..",
  "!": "-.-.--",
  "-": "-....-",
  "/": "-..-.",
  "@": ".--.-.",
  "(": "-.--.",
  "\)": "-.--.-",
  " ": "\xa0\xa0\xa0"
};
const morse = {
  "-----": "0",
  ".----": "1",
  "..---": "2",
  "...--": "3",
  "....-": "4",
  ".....": "5",
  "-....": "6",
  "--...": "7",
  "---..": "8",
  "----.": "9",
  ".-": "a",
  "-...": "b",
  "-.-.": "c",
  "-..": "d",
  ".": "e",
  "..-.": "f",
  "--.": "g",
  "....": "h",
  "..": "i",
  ".---": "j",
  "-.-": "k",
  ".-..": "l",
  "--": "m",
  "-.": "n",
  "---": "o",
  ".--.": "p",
  "--.-": "q",
  ".-.": "r",
  "...": "s",
  "-": "t",
  "..-": "u",
  "...-": "v",
  ".--": "w",
  "-..-": "x",
  "-.--": "y",
  "--..": "z",
  ".-.-.-": ".",
  "--..--": ",",
  "..--..": "?",
  "-.-.--": "!",
  "-....-": "-",
  "-..-.": "/",
  ".--.-.": "@",
  "-.--.": "(",
  "-.--.-": ")",
  " ": "\xa0"
}

// abc to morse
const encode = () => {
  return encoder.value.toString().toLowerCase().split('').map(e => abc[e] + ' ').join('   ');
};

// morse to abc
const decode = () => {
  return decoder.value.toString().split('   ').map(e => e.split(' ').map(f => morse[f]).join('')).join(' ')
};

</script>

<style scoped>

input {
  width: 100%;
  max-width: 100%;
}
p {
  height: 1.5rem;
  margin: .25rem;
}
</style>