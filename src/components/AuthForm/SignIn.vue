<script setup>
import AuthIcon from '@/components/ui/icons/AuthIcon.vue';
import AppBtn   from '@/components/ui/AppBtn.vue';
import AuthWraper from '@/components/AuthForm/AuthWraper.vue';

const login = async function (ev) {
  ev.preventDefault();
  try {
    const response = await fetch('https://dist.nd.ru/api/auth', {
      mode: 'no-cors',
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
      },
      credentials: 'include',
      body: JSON.stringify({
        email: 'user@example.com',
        password: '123',
      }),
    });

    const data = await response.json();

    if (response.status === 200 || response.status === 201) {
      /*не реактивный лучше vuex*/
      localStorage.setItem('user', JSON.stringify(data));
      /*vuex*/
      // this.$store.dispatch('user/setUser', data)
      /*Нажо закрыть модалку*/
    } else {
      this.error = data;
      console.error(data);
    }
  } catch (err) {
    console.log('ERROR', err);
  }
}
</script>

<template>
  <AuthWraper>
    <template #title>
      Войти
    </template>
    <!-- todo элементы формф стоит вынести в ui так же обезличенно добавить
     пропсы чтобы можно было передавать любые инпуты селекты
     form__label сделать пропсом разместить его по умолчанию в slot label
     -->
    <form class="form auth-form__form" action="" method="post" @submit="login">
      <label class="form__input">
        <span class="form__label">Email</span>
        <input class="input" placeholder="Введите значение" type="text">
        <span class="form__error">Сообщение об ошибке</span>
      </label>
      <label class="form__input">
        <span class="form__label">Пароль</span>
        <input class="input" placeholder="Введите пароль" type="text">
        <span class="form__error">Сообщение об ошибке</span>
      </label>
      <div class="form__wrapper">
        <div class="auth-form__link">
          У вас нет аккаунта?
          <a class="link" href="javascript:void(0)" @click.prevent="$emit('swapForm')">Зарегистрируйтесь</a>
        </div>

        <AppBtn type="submit">
          <AuthIcon />
          Войти
        </AppBtn>
      </div>
      <div class="form__notice">
        Пользователь с таким логином не найден
      </div>
    </form>
  </AuthWraper>
</template>

<style module="$s" lang="scss">

</style>
