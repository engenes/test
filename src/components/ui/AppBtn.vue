<script setup>
import { defineProps } from 'vue';

defineProps({
  label: String,
});
</script>

<template>
  <button class="btn" @click="$emit('click', $event)">
    <slot>{{ label }}</slot>
  </button>
</template>

<style lang="scss" scoped>
.btn {
  display: flex;
  justify-content: center;
  align-items: center;
  border: none;
  border-radius: 32px;
  background-color: #B1C909;
  font-size: 20px;
  font-style: normal;
  font-weight: 500;
  width: 100%;
  min-height: 56px;
  color: #fff;
  cursor: pointer;
  /*ToDo: Вынести ширину в миксины мест где вставляются*/
  max-width: 144px;

  &:hover {
    background-color: #97AB0D;
    transition: all linear 0.3s;
  }

  &:active {
    background-color: #819400;
    transition: all linear 0.3s;
  }

  &:disabled {
    background-color: #9DA5AF;
  }
}
</style>
