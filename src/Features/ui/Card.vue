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
        <div class="card__price-container">
          <span class="price-container__actual">5 990 &#8381</span>
          <del class="price-container__not-actual">5 990 &#8381</del>
        </div>
      </div>
      <Button class="card__button">Купить</Button>
    </div>
  </template>
  <script setup>
  import { computed } from "vue";
  import {Button} from '../../Shared';
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
  <style lang="scss" >
  @import "../../Shared/variables.scss";
  .card {
    display: flex;
    flex-direction: column;  
    gap: 16px;
    &:hover .card__desc{
      transition: .3s;
      color:$color-font-hover;
    }
    &:hover .card__item{
      transition: .3s;
      transform: scale(1.3);
  
    }
    &__img {
      display: flex;
      justify-content: center;
      position: relative;
      height: 200px;
      background-color: $color-card-bg;
  
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
      border:1px solid $scroll-bar;
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
      margin-bottom: -14px;
    }
    &__spec {
      display: flex;
      flex-direction: column;
      gap: 16px;
    }
    &__desc {
      font-size: 14px;
    }
    &__button{
      align-self: flex-start;
      padding: 8px 14px ;
      border-radius: 4px;
      color:$color-brand;
      font-weight: 700;
      font-size: 13px;
      line-height: 20px;
    }
  }
  .price-container {
    display: flex;
    &__actual {
      margin-right: 8px;
      font-weight: 700
    }
    &__not-actual {
      font-size: 12px;
      color: $color-font-second;
    }
  }
  </style>
  
