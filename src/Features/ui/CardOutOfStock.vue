<template>
  <div class="card">
    <a href="#" class="card__img">
      <div class="card__hot">
        <span>Хит продаж</span>
        <img src="../../Shared/Assets/fire.svg" alt="hot" />
      </div>
      <img class="card__item" src="../../Shared/Assets/item.png" alt="item" />
      <span class="card__discount">25%</span>
    </a>
    <div class="card__spec">
      <p class="card__brand">Бренд</p>
      <p class="card__desc">
        {{ description }}
      </p>
    </div>
    <Button class="card__button">Сообщить о поступлении</Button>
  </div>
</template>
<script setup>
import { computed } from "vue";
import { Button } from "../../Shared";
const props = defineProps({
  text: String,
});
const description = computed(() => {
  if (props.text?.length! > 60) {
    return props.text!.slice(0, 79) + "...";
  }
  return props.text;
});
</script>
<style lang="scss" scoped>
@import "../../Shared/variables.scss";
@import "../../Shared/media.scss";
.card {
  display: flex;
  flex-direction: column;
  gap: 16px;
  &:hover .card__desc {
    transition: 0.3s;
    color: $color-font-hover;
  }
  &:hover .card__item {
    transition: 0.3s;
    transform: scale(1.3);
  }
  &__img {
    display: flex;
    justify-content: center;
    position: relative;
    height: 200px;
    background-color: $color-white;
  }
  &__hot {
    position: absolute;
    display: flex;
    align-items: center;
    text-wrap: nowrap;
    top: 12px;
    left: 12px;
    padding: 0px 8px;
    font-size: 14px;
    border-radius: 4px;
    border: 1px solid $scroll-bar;
    background-color: $color-white;
  }
  &__item {
    align-self: center;
    opacity: 0.5;
  }
  &__discount {
    display: block;
    position: absolute;
    bottom: 12px;
    left: 12px;
    padding: 4px 10px;
    border-radius: 4px;
    font-weight: 700;
    color: $color-white;
    background-color: $color-brand;
  }
  &__brand {
    font-size: 14px;
    color: $color-font-second;
  }
  &__spec {
    display: flex;
    flex-direction: column;
    flex: 1;
    gap: 16px;
  }
  &__desc {
    font-size: 14px;
  }
  &__button {
    width: 100%;
    border-radius: 4px;
    color: $color-border;
    border: 1px solid $color-border;
  }
}
</style>
