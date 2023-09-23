<script setup>
  const props = defineProps({
    type: {
      type: String,
      default: 'button'
    },
    label: {
      type: String,
      default: 'Кнопка'
    },
    color: {
      type: String,
      default: 'secondary'
    },
    disabled: {
      type: Boolean,
      required: false
    },
  })

  const emit = defineEmits(['click'])

  const clickButton = () => { emit('click') }
</script>

<template>
  <button 
    :type="type" 
    :class="['button', `button--${color}`]"
    :disabled="disabled"
    @click="clickButton"
    >{{ label }}
  </button>
</template>

<style lang='scss' scoped>
  .button {
    $this: &;

    display: inline-flex;
    align-items: center;
    justify-content: center;
    user-select: none;
    white-space: nowrap;
    border-radius: 4px;
    font-weight: 600;
    font-size: 16px;
    transition: all var(--base-duration);
    border: 2px solid transparent;
    padding: 0 20px;
    height: 48px;
    &#{$this}--secondary {
      color: var(--ink-light, #5F5F5F);
      background-color: var(--white);
      border-color: var(--sky-darkest, #E6E6E6);
      &:hover { background-color: var(--btn-secondary-hover); }
      &:active, &.active { background-color: var(--btn-secondary-active); border-color: transparent; }
      &:disabled { 
        background-color: var(--btn-secondary-disabled);
        border-color: transparent;
        color: rgba(95,95,95, .6); 
      }
    }
    &#{$this}--primary {
      background-color: var(--orange-base, #F60);
      color: var(--white);
      &:hover { background-color: var(--btn-primary-hover); }
      &:active, &.active { background-color: var(--btn-primary-active); }
      &:disabled { background-color: var(--btn-primary-disabled); }
    }
    &#{$this}--outline {
      background-color: var(--white);
      border-color: var(--orange-base, #F60);
      color: var(--orange-base, #F60);
      &:hover { border-color: var(--btn-primary-hover); color: var(--btn-primary-hover); }
      &:active, &.active { border-color: var(--btn-primary-active); color: var(--btn-primary-active); }
      &:disabled { border-color: var(--btn-primary-disabled); color: var(--btn-primary-disabled); }
    }
  }
</style>