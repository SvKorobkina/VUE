<template>
  <!--Правая панель сайта-->
  <div class="right">
    <!--Добавление области, содержащей 4 блока: "начать работу", "уведомления", "обучение", "достижения" -->
    <div class="work">
      <div class="work1">
        <!--Помещает область "начать работу" в верхний левый угол блока "work"-->
        <div class="scalable">
          <!--Блок, отвечающий за движение при наведении курсора -->
          <img src="../assets/start_work.png" alt="Изображение отсутствует" />
        </div>
      </div>
      <div class="work2">
        <!--Помещает область "уведомление" в правый верхний угол блока "work"-->
        <div class="scalable">
          <div class="base">
            <!--Добавление индикатора уведомлений-->
            <div class="indicator">2</div>
          </div>
          <img src="../assets/notice.png" alt="Изображение отсутствует" />
        </div>
      </div>
      <div class="work3">
        <!--Помещает область "обучение" в нижний левый угол блока "work"-->
        <div class="scalable">
          <img src="../assets/education.png" alt="Изображение отсутствует" />
        </div>
      </div>
      <div class="work4">
        <!--Помещает область "достижения" в нижний правый угол блока "work"-->
        <div class="scalable">
          <img src="../assets/progress.png" alt="Изображение отсутствует" />
        </div>
      </div>
    </div>
  </div>
</template>
