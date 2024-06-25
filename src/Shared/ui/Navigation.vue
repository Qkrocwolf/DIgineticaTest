<template>
  <nav class="nav">
    <ul class="nav__ul">
      <li class="nav__li"><a href="#">Информация о компании</a></li>
      <li class="nav__li"><a href="#">Контакты</a></li>
      <li class="nav__li"><a href="#">Полезные ссылки</a></li>
    </ul>
  </nav>
</template>
<style lang="scss">
@import "../variables.scss";
@import "../media.scss";
.nav {
  &__ul {
    display: flex;
    gap: 20px;
    @include md {
      gap: 8px;
    }
  }
  &__li {
    font-size: 14px;
    line-height: 17px;
    list-style: none;
    transition: 0.3s;
    text-wrap: nowrap;
    & a:hover {
      color: $color-font-hover;
    }
  }
}
</style>
