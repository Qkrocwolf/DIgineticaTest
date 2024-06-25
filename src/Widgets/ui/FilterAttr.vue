<template>
  <div class="filter-attr">
    <div class="filter-attr__header">
      <h3 class="filter-attr__label">Бренд</h3>
      <button class="filter-attr__clear" @click="checked.length = 0">
        Очистить
      </button>
    </div>
    <Search placeholder="Поиск" />
    <div class="filter-attr__attr-container">
      <ul class="filter-attr__list">
        <li v-for="(item, index) in 9" class="filter-attr__item">
          <label class="filter-attr__list-label">
            <input
              type="checkbox"
              :id="index.toString()"
              name="brand"
              class="filter-attr__checkbox checkbox"
              v-model="checked"
              :value="item"
            />
            <span class="checkbox__custom"></span>Атрибут</label
          ><span class="filter-attr__count">3</span>
        </li>
      </ul>
      <h3 class="filter-attr__size-label">Размер</h3>
      <ul class="filter-attr__list">
        <li v-for="(item, index) in 9" class="filter-attr__item">
          <label class="filter-attr__list-label">
            <input
              type="checkbox"
              :id="index.toString()"
              name="size"
              class="filter-attr__checkbox checkbox"
              v-model="checked"
              :value="item + 10"
            /><span class="checkbox__custom"></span>Атрибут</label
          ><span class="filter-attr__count">3</span>
        </li>
      </ul>
    </div>
  </div>
</template>
<script setup>
import { Search } from "../../Features";
import { ref } from "vue";
const checked = ref([]);
</script>
<style lang="scss">
@import "../../Shared/variables.scss";
.filter-attr {
  display: flex;
  flex-direction: column;
  gap: 16px;
  &__header {
    display: flex;
    justify-content: space-between;
  }
  &__label {
    font-size: 16px;
  }
  &__clear {
    font-size: 12px;
    align-self: flex-end;
    color: $color-font-second;
    text-decoration: underline;
    background-color: transparent;
    border: none;
    cursor: pointer;
    &:hover {
      color: black;
    }
  }
  &__search {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 8px;
    padding: 0px 12px;
    height: 40px;
    border: 1px solid $color-border;
    border-radius: 4px;
    &:hover {
      border: 1px solid $color-brand;
    }
    &:has(.filter-attr__input:focus) {
      border: 1px solid $color-brand;
    }
  }
  &__glass {
    width: 16px;
    height: 16px;
    opacity: 0.6;
  }
  &__input {
    flex: 1;
    border: none;
    outline: none;
  }
  &__item {
    padding-right: 16px;
    display: flex;
    align-items: center;
    gap: 10px;
    transition: 0.3s;
  }

  &__list {
    display: flex;
    flex-direction: column;
  }
  &__list-label {
    padding: 5px 0px 5px 0px;
    display: flex;
    align-items: center;
    font-size: 14px;
    flex: 1;
    cursor: pointer;
    &:hover {
      background-color: $color-font-bg;
    }
    &:hover > .checkbox__custom {
      border: 1px solid $color_brand;
    }
  }
  &__size-label {
    margin: 16px 0;
    text-align: center;
    font-size: 16px;
  }
  &__count {
    font-size: 12px;
    opacity: 0.6;
  }
  &__attr-container {
    overflow-y: scroll;
    height: 400px;
  }
  &__button {
    background-color: $color-white;
    border: none;
  }
}
.checkbox {
  width: 0;
  height: 0;
  opacity: 0;
  position: absolute;
  z-index: 1;
  &__custom {
    position: relative;
    display: inline-block;
    width: 20px;
    height: 20px;
    margin-right: 10px;
    border-radius: 3px;
    border: 1px solid $color-border;

    &::before {
      content: "";
      display: inline-block;
      width: 13px;
      height: 13px;
      background: url("../../Shared/Assets/checkbox.svg");
      background-size: contain;
      background-repeat: no-repeat;
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%) scale(0);
      transition: 0.1s ease-in;
    }
  }
  &:checked + &__custom::before {
    transform: translate(-50%, -50%) scale(1);
  }
  &:checked + &__custom {
    background-color: $color-brand;
  }
}
</style>
