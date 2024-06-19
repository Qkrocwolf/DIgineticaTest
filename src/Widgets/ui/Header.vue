<template>
  <div class="header">
    <div class="header__logo-catalog">
      <Logo class="header__logo" />
      <Button class="header__button-catalog">Каталог</Button>
    </div>
    <Search
      class="header__search"
      :with-search-button="true"
      placeholder="Поиск по 100 000 товаров"
    />
    <Navigation class="header__navigation" />
  </div>
</template>
<script setup lang="ts">
import { Logo, Button, Navigation } from "../../Shared";
import { Search } from "../../Features";
</script>
<style lang="scss">
@import "../../Shared/variables.scss";
@import "../../Shared/media.scss";
.header {
  display: flex;
  align-items: center;
  padding: 12px 0;
  gap: 24px;
  @include md {
    gap: 8px;
  }
  &__search {
    flex: 1;
  }
  &__logo-catalog {
    display: flex;
    gap: 8px;
    @include xs {
      display: none;
    }
  }
  &__logo {
    margin: 0 24px 0 24px;
  }
  &__navigation {
    @include ml {
      display: none;
    }
  }
  &__button-catalog {
    font-weight: 500;
    letter-spacing: 0.3px;
    padding: 15px 26px;
  }
}
</style>
