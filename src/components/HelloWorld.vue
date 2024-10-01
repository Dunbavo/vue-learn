<script setup>
import { ref } from 'vue'

defineProps({
  msg: String,
})

const count = ref(0)

const rawHtml = '<span style="color: red">Красный текст.</span>'

const isButtonDisabled = true

const objectOfAttrs = {
  id: 'container',
  class: 'wrapper',
  style: 'background-color:grey; color:white; border-radius:5px'
}
function numder() {
  return Math.round(Math.random () * 100);
}

const message = 'строка'

function data() {
    return {
      imageAttr: 'src',  // Атрибут, который будет динамически подставлен (src)
      imageSrc: 'https://avatars.dzeninfra.ru/get-zen_doc/4909844/pub_63f610bd43c2e373bc2a7f3e_63f610fb593b986e4c72b199/scale_1200'  // Значение для src
    };
}

</script>

<template>
  <h1>{{ msg }}</h1>

  <div class="card">
    <button type="button" @click="count++">count is {{ count }}</button>
  </div>

  <p>Двойные фигурные скобки: {{ rawHtml }}</p>
  <p>Директива v-html: <span v-html="rawHtml"></span></p>

  <button :disabled="isButtonDisabled">Кнопка</button>

  <p v-bind="objectOfAttrs">Динамическая привязка нескольких атрибутов</p>

  <p>Рандомное число + 1: {{ numder() + 1 }}</p>

<!--  <input type="text" value="'YES' или 'NO'?" />-->

  <p>'true' или 'false'?<br>{{ ok ? 'ok = true' : 'ok = false' }}</p>

  <p>Строка => {{ message.split('').reverse().join('') }}</p>

  <p v-if="isButtonDisabled">Сейчас меня видно</p>

  <div>
    <img v-bind:[imageAttr]="imageSrc" alt="Dynamic Image">
  </div>

</template>

<style scoped>

</style>
