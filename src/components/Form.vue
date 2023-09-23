<script setup>
  import Form from '@/components/Form.vue'
  import Button from '@/components/Button.vue'
  import { ref } from 'vue';

  const value = ref('');
  const textareaMaxCounter = 250;
  function textareaCounter() {
    if (value.value.length >= textareaMaxCounter) {
      value.value = value.value.substring(0,textareaMaxCounter);
    }
  }
  const sendForm = () => alert('Форма отправлена');
  
</script>

<template>
  <div class="v-form">
    <div class="v-form__top">
      <span>Дополнительные данные</span>
      <p>Вы можете указать любую информацию, например, размер спецодежды</p>
    </div>
    <div class="v-form__main">
      <form action="/">
        <div class="v-form__group">
          <div class="v-form__item">
            <label>Размер обуви</label>
            <input type="text" name="shoe">
          </div>
          <div class="v-form__item">
            <label>Размер одежды</label>
            <input type="text" name="clothing">
          </div>
        </div>
        <div class="v-form__item">
          <label>Комментарии</label>
          <textarea name="comments" v-model="value" @input="textareaCounter()"></textarea>
          <div class="v-form__counter">
            {{ value.length }}/250
          </div>
        </div>
        <div class="v-form__btn">
          <Button label="Отмена"/>
          <Button label="Сохранить" color="primary" type="submit" @click="sendForm" />
        </div>
      </form>
    </div>
  </div>
</template>

<style lang='scss' scoped>
  .v-form {
    flex: 1;
    background-color: var(--white);
    border-radius: 8px;
    &__top {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      padding: 19px 24px;
      border-bottom: 1px solid var(--sky-darkest, #E6E6E6);
      span {
        font-weight: 600;
        line-height: 18px;
        color: var(--base-black);
      }
      p {
        font-size: 14px;
        line-height: 18px;
        color: var(--gray);
      }
    }
    &__main {
      padding: 24px;
    }
    &__group {
      display: flex;
      gap: 16px;
      margin-bottom: 16px;
    }
    &__item {
      flex: 1;
      label {
        display: inline-block;
        color: var(--ink-light, #5F5F5F);
        margin-bottom: 6px;
        font-size: 14px;
      }
      input,
      textarea {
        width: 100%;
        border-radius: 6px;
        padding: 7px 14px;
        border: 1px solid var(--sky-darkest, #E6E6E6);
      }
      input {
        height: 36px;
      }
      textarea { height: 96px; }
    }
    &__btn {
      display: flex;
      justify-content: flex-end;
      gap: 16px;
      margin-top: 24px;
    }
    &__counter {
      display: flex;
      justify-content: flex-end;
      color: var(--gray);
      font-size: 12px;
      margin-top: 4px;
    }
  }
</style>