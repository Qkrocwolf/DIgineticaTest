<template>
  <div class="container">
    <Header />
    <div class="container__main">
      <div class="container__filter">
        <Category />
        <Price />
        <FilterAttr />
      </div>
      <ShowCase class="container__show-case"></ShowCase>
    </div>
  </div>
</template>
<script setup lang="ts">
import { Header, ShowCase, Price, Category, FilterAttr } from "../Widgets";
</script>
<style lang="scss">
@import "../Shared/media.scss";
.container {
  margin: 0 auto;
  padding: 0 100px 36px 100px;
  @include md {
    padding: 0 20px 20px 20px;
  }
  &__main {
    margin-top: 24px;
    display: flex;
    gap: 36px;
  }
  &__filter {
    font-family: "PT Sans", sans-serif;
    min-width: 280px;
    display: flex;
    flex-direction: column;
    gap: 28px;
    @include xs {
      display: none;
    }
  }
}
</style>
