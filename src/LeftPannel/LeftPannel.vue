<template>
  <!--Левая панель сайта-->
  <div class="info">
    <div class="info_flex">
      <div class="fio">
        <!--Блок левой верхней панели, включающей дату/время, выход, смену темы и ФИО-->
        <div class="upper_pannel">
          <div class="fio-item item1">
            {{ date }}
            <!--Объявление переменных для даты и времени-->
            <br />
            {{ time }}
          </div>
          <div class="fio-item item2">
            <a href="#">
              <!--Выход из ЛК-->
              <img src="../assets/exit.png" alt="Изображение отсутствует" />
            </a>
          </div>
        </div>
        <div class="fio-item item3">
          <button
            class="theme-button"
            @click="
              emit('changeTheme', props.theme === 'dark' ? 'light' : 'dark')
            "
          >
            <!--Кнопка переключения темной/светлой темы-->
            <img v-if="props.theme === 'dark'" src="../assets/light.png" />
            <!--Добавление соответствующего изобрежения кнопке, в зависимости от выполнения условия: theme принимает значение 'dark' или 'light' -->
            <img v-if="props.theme === 'light'" src="../assets/dark.png" />
          </button>
        </div>
        <div class="fio-item item4" style="font-size: 30px">
          Фамилия Имя Отчество
          <br />
          xx:xx:xxxx
          <div style="font-size: 14px">
            Таб №: ГОКИ 0000 <br />
            Проходчик |V разряда
          </div>
        </div>
      </div>
    </div>
    <div class="fio2">
      <!--Блок нижней левой панели  -->
      <div class="fio2-item div1">
        <div class="box_inside">
          <button type="button" class="button">Инструктаж</button>
          <PieBlock bg="#353d54" color="#b1d63b" :percent="100">
            <img src="../assets/note.png" alt=""> 
          </PieBlock>
          <!--Блок с круговой диаграммой-->
        </div>
      </div>
      <div class="fio2-item div2">
        <div class="box_inside">
          <button type="button" class="button">
            Предсменный <br />
            экзаменатор
          </button>
          <PieBlock bg="#353d54" color="#b1d63b" :percent="100">
            <img src="../assets/test.png" alt="">
          </PieBlock>
        </div>
      </div>
      <div class="fio2-item div3">
        <div class="box_inside">
          <button type="button" class="button">
            Тестов <br />
            выполнено
          </button>
          <PieBlock bg="#353d54" color="#b1d63b" :percent="25">
            12
          </PieBlock>
        </div>
      </div>
      <div class="fio2-item div4">
        <div class="box_inside">
          <button type="button" class="button">
            Аттестация <br />
            через
          </button>

          <PieBlock bg="#353d54" color="#ee7e1a" :percent="10">
            3
            <div style="font-size: 18px">дня</div>
          </PieBlock>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";
import PieBlock from "../PieBlock/PieBlock.vue";
const props = defineProps({
  //Объявляем переменную theme - 'dark' для состояния по умолчанию
  theme: {
    type: String,
    default: "dark",
  },
});
const emit = defineEmits(["changeTheme"]); //Передаем параметр 'changeTheme'
const date = ref("");
const time = ref("");
let timer;
const pad = (s) => String(s).padStart(2, "0");
onMounted(() => {
  timer = setInterval(() => {
    const now = new Date();
    const d = pad(now.getDate());
    const m = pad(now.getMonth() + 1);
    const y = now.getFullYear();
    const h = pad(now.getHours());
    const i = pad(now.getMinutes());
    date.value = `${d}.${m}.${y}`;
    time.value = `${h}:${i}`;
  }, 1000);
});
onUnmounted(() => {
  clearInterval(timer);
});
</script>
