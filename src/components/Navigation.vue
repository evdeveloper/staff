<script setup>

</script>

<template>
  <div class="v-navigation">
    <a href="#" class="v-navigation__link active">Основная информация</a>
    <a href="#" class="v-navigation__link">Квалификационные документы</a>
    <a href="#" class="v-navigation__link">Опыт работы</a>
    <a href="#" class="v-navigation__link">Образование</a>
    <a href="#" class="v-navigation__link">Контакты</a>
    <a href="#" class="v-navigation__link">Данные для расчётов</a>
    <a href="#" class="v-navigation__link">Виды работ</a>
    <a href="#" class="v-navigation__link">Дополнительные данные</a>
  </div>
</template>

<style lang='scss' scoped>
  .v-navigation {
    display: flex;
    flex-direction: column;
    flex: 0 0 380px;
    gap: 4px;
    padding: 24px;
    border-radius: 8px;
    background-color: var(--white);
    &__link {
      padding: 8px 16px;
      border-radius: 4px;
      color: var(--base-black);
      transition: all var(--base-duration);
      &:hover, &.active {
        color: var(--white);
        background: var(--ink-light, #5F5F5F);
      }
    }
  }
</style>