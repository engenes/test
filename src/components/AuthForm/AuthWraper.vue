<template>
  <aside class="auth-form">
    <h2 v-if="$slots.title">
      <slot name="title" />
    </h2>
    <slot />
  </aside>
</template>

<style lang="scss">
.auth-form {
  &__link {
    color: #9DA5AF;
    text-overflow: ellipsis;
    /* Text-small */
    font-family: Montserrat;
    font-size: 18px;
    font-style: normal;
    font-weight: 400;
    line-height: 28px; /* 155.556% */

    @media (max-width: 767px) {
      font-size: 14px;
      line-height: 24px; /* 171.429% */
      margin-top: 12px;
    }
  }
}
</style>
