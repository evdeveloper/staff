<script setup>
  import Form from '@/components/Form.vue'
  import Navigation from '@/components/Navigation.vue';
</script>

<template>
  <div class="v-main">
    <header class="v-main__header">
      <div class="v-main__header-col">
        <a href="#" class="v-main__header-link">
          <img src="@/assets/img/svg/vacancy.svg" alt="Вакансии">
          Вакансии
        </a>
        <a href="#" class="v-main__header-link">
          <img src="@/assets/img/svg/building.svg" alt="Объекты">
          Объекты
        </a>
      </div>
      <div class="v-main__header-col">
        <div class="v-main__header-inner">
          <a href="#" class="v-main__header-item v-main__header-actions">
            <img src="@/assets/img/svg/heart.svg" alt="Избранное">
            <span>Избранное</span>
          </a>
          <a href="#" class="v-main__header-item v-main__header-actions">
            <img src="@/assets/img/svg/bell.svg" alt="Уведомления">
            <span>Уведомления</span>
          </a>
          <a href="#" class="v-main__header-item">
            <div class="v-main__user">АБ</div>
            <span>Профиль</span>
          </a>
        </div>
      </div>
    </header>
    <main class="v-main__content">
      <div class="v-main__content-top">
        <a href="#" class="v-main__prev">
          <img src="@/assets/img/svg/chevron-right.svg" alt="Назад">
          Назад
        </a>
        <h1>Редактировать профиль</h1>
      </div>
      <div class="v-main__inner">
        <Form />
        <Navigation />
      </div>
    </main>
  </div>
</template>

<style lang='scss' scoped>
  .v-main {
    width: 100%;
    flex: 1;
    height: 100vh;
    background-color: var(--BGN, #FAFAFA);
    &__header {
      display: flex;
      justify-content: space-between;
      padding: 16px 24px;
      height: 80px;
      border-bottom: 1px solid var(--sky-darkest);
      &-inner {
        display: flex;
        gap: 24px;
      }
      &-link {
        display: flex;
        align-items: center;
        font-weight: 500;
        font-size: 20px;
        gap: 8px;
        color: var(--base-black);
        &:not(:last-child) { margin-right: 48px; }
      }
      &-item {
        display: flex;
        align-items: center;
        gap: 8px;
        span {
          font-weight: 600;
          font-family: var(--Inter-font);
          font-size: 14px;
          color: var(--ink-light);
        }
      }
      &-col {
        display: flex;
        align-items: center;
      }
      &-actions {
        padding: 8px;
      }
    }
    &__user {
      display: flex;
      align-items: center;
      justify-content: center;
      width: 48px;
      height: 48px;
      border-radius: 100px;
      border: 1px solid var(--sky-darkest, #E6E6E6);
      background-color: var(--white);
      font-size: 20px;
      font-family: var(--OpenSans-font);
      font-weight: 600;
      color: var(--gray);
    }
    &__prev {
      display: flex;
      align-items: center;
      gap: 4px;
      padding: 10px 16px 10px 8px;
      border-radius: 4px;
      background-color: var(--white);
      border: 1px solid var(--sky-darkest, #E6E6E6);
      color: var(--ink-light, #5F5F5F);
      font-weight: 600;
    }
    &__content {
      overflow: auto;
      height: calc(100vh - 80px);
      padding: 25px 24px;
      &-top {
        display: flex;
        align-items: center;
        gap: 16px;
        margin-bottom: 19px;
      }
    }
    &__inner {
      display: flex;
      gap: 24px;
    }
  }

</style>