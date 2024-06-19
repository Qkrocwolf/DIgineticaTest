<template>
  <div class="category">
    <p class="category__name">
      <a href="#" class="category__link"> Категории</a>
      <span class="category__count">3</span>
    </p>
    <ul class="category__list">
      <li
        v-for="index in 3"
        class="category__item"
        @click="isActive = index"
        :class="{ active: isActive === index }"
      >
        <a href="#" class="category__link"> Название категории </a>
        <span class="category__count">3</span>
      </li>
    </ul>
  </div>
</template>
<script setup lang="ts">
import { ref } from "vue";
const isActive = ref(0);
</script>
<style lang="scss">
@import "../../Shared/variables.scss";
.category {
  &__name {
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-radius: 5px;
    padding: 0px 16px 0px 8px;
    font-size: 14px;
    height: 30px;
  }
  &__item {
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-radius: 5px;
    padding: 0px 16px 0px 32px;
    font-size: 14px;
    height: 30px;
  }
  &__count {
    font-size: 12px;
    opacity: 0.6;
  }
  &__link {
    width: 100%;
    &:hover {
      color: $color-brand;
    }
  }
}
.active {
  background-color: $color-brand;
  &:hover .category__link {
    color: black;
  }
}
</style>
