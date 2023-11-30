<template>
  <header class="header">
    <div class="row">
      <div class="header__grid">
        <TheLogo />
        <AppBtn label="Вход" @click="openModal" />
      </div>
    </div>
  </header>
</template>

<script setup>
import TheLogo from '@/components/Logo/Logo';
import AppBtn  from '@/components/ui/AppBtn.vue';

const openModal = () => {
  const modal = document.querySelector('.popup');
  modal.classList.add('show');
  document.querySelector('body').classList.add('hidden');
};
</script>

<style lang="scss">
.header {

  &__grid {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-top: 40px;
    padding-bottom: 40px;

    @media (max-width: 1690px) {
      padding-top: 20px;
      padding-bottom: 19px;
    }

    @media (max-width: 1365px) {
      padding-bottom: 61px;
    }

    @media (max-width: 767px) {
      padding-bottom: 40px;
    }
  }
}
</style>
