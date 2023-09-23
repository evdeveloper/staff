<template>
  <div class="v-sidebar">
    <div class="v-sidebar__top">
      <a href="#" class="v-sidebar__logo logo">
        <img src="@/assets/img/svg/logo-white.svg" alt="Кадры">
      </a>
    </div>
    <div class="v-sidebar__main">
      <nav class="v-sidebar__menu">
        <div class="v-sidebar__title">Профиль</div>
        <div class="v-sidebar__item">
          <a href="#" class="v-sidebar__link active">Обо мне</a>
          <a href="#" class="v-sidebar__link">Документы</a>
        </div>
        <div class="v-sidebar__title">Моя работа</div>
        <div class="v-sidebar__item">
          <a href="#" class="v-sidebar__link">Объекты</a>
          <a href="#" class="v-sidebar__link">Календарь работ</a>
          <a href="#" class="v-sidebar__link">Отклики</a>
        </div>
      </nav>
    </div>
  </div>
</template>

<style lang="scss" scoped>
  .v-sidebar {
    width: 240px;
    height: 100vh;
    display: flex;
    flex-direction: column;
    gap: 16px;
    flex: 0 0 auto;
    background: var(--sidebar-gradient);
    &__main {
      padding: 0 8px;
    }
    &__top {
      padding: 27px 24px 19px;
    }
    &__title {
      font-size: 12px;
      color: var(--ink-light);
      padding: 13px 24px;
      margin: 0 -8px;
    }
    &__item {
      &:not(:last-child) { margin-bottom: 16px; }
    }
    &__link {
      display: flex;
      align-items: center;
      font-weight: 600;
      height: 40px;
      padding: 8px 16px;
      border-radius: 4px;
      color: rgba(255,255,255, 0.6);
      transition: all var(--base-duration);
      &:not(:last-child) { margin-bottom: 4px; }
      &:hover, &.active {
        background-color: var(--ink-light);
        color: var(--white);
      }
    }
  }
</style>