<template>
  <div class="row-box" :class="'theme-' + theme"><!--Задаем класс theme для родительского блока row-box-->
    <img src="./assets/logo.jpg" class="logo" alt="Amicum"> <!--Вставка логотипа -->
    <div class="main">
      <LeftPannel :theme="theme" @changeTheme="value => theme = value" />
      <RightPannel :theme="theme" />
    </div>
  </div>
</template>

<script setup>
//Импорт переменной ref
import { ref } from 'vue' 
//Импорт модулей
import LeftPannel from './LeftPannel/LeftPannel.vue'
import RightPannel from './RightPannel/RightPannel.vue'
const theme = ref('dark') //Указываем, что ref по умолчанию - темная тема
</script>


<style src="./global.css"></style> <!--Подключение css -->
