<template>
  <div class="app">
    <TheHeader />
    <MainScreen />
    <AppPopup />
  </div>
</template>

<script setup>
import TheHeader  from '@/components/Header/TheHeader';
import MainScreen from '@/components/MainScreen/MainScreen';
import AppPopup   from '@/components/ui/Popup/AppPopup';
</script>

<style lang="scss">
.form {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 40px;

  @media (max-width: 767px) {
    margin-top: 28px;
  }

  &__input {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    width: 100%;

    &:first-child {
      margin-bottom: 24px;

      @media (max-width: 767px) {
        margin-bottom: 16px;
      }
    }
  }

  &__label {
    color: #9DA5AF;
    text-overflow: ellipsis;
    font-size: 18px;
    font-style: normal;
    font-weight: 400;
    line-height: 28px; /* 155.556% */
    margin-bottom: 8px;
    margin-left: 25px;
  }

  &__wrapper {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-top: 40px;
    width: 100%;

    @media (max-width: 767px) {
      flex-direction: column-reverse;
      margin-top: 28px;
    }

    .btn {
      display: inline-block;
      max-width: none;
      width: auto;
      padding-right: 24px;
      padding-left: 24px;

      @media (max-width: 767px) {
        max-width: none;
      }
    }
  }

  &__error {
    color: #FF7461;
    text-overflow: ellipsis;
    font-family: Montserrat;
    font-size: 18px;
    font-style: normal;
    font-weight: 400;
    line-height: 28px; /* 155.556% */
    display: none;
  }

  &__notice {
    display: none;
    border-radius: 24px;
    padding: 8px 20px;
    background-color: rgba(255, 116, 97, 0.1);

    color: #FF7461;
    text-overflow: ellipsis;
    /* Text-small */
    font-family: Montserrat;
    font-size: 18px;
    font-style: normal;
    font-weight: 400;
    line-height: 28px; /* 155.556% */
    margin-top: 20px;
    width: 100%;
  }
}

.input {
  padding-right: 25px;
  padding-left: 25px;
  border-radius: 36px;
  color: #0A1F38;
  text-overflow: ellipsis;
  white-space: nowrap;
  /* Text-small */
  font-family: Montserrat;
  font-size: 18px;
  font-style: normal;
  font-weight: 400;
  line-height: 28px; /* 155.556% */
  width: 100%;
  min-height: 72px;
  border: 2px solid transparent;

  &::placeholder {
    color: #9DA5AF;
    text-overflow: ellipsis;
    font-family: Montserrat;
    font-size: 18px;
    font-style: normal;
    font-weight: 400;
    line-height: 28px; /* 155.556% */
  }

  &:hover {
    border: 2px solid #B1C909;
    transition: all linear 0.3s;
  }

  &:focus {
    border: 2px solid #B1C909;
    transition: all linear 0.3s;
  }
}
</style>
