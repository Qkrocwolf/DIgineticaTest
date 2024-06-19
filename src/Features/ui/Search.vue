<template>
  <div class="search">
    <ButtonSearch />
    <input
      class="search__field"
      :placeholder="placeholder"
      v-model="inputValue"
    />
    <ButtonClearInput
      v-if="inputValue"
      @click="inputValue = ''"
      class="search__clear-button"
    />
    <Button class="search__button" v-if="inputValue && withSearchButton"
      >Найти</Button
    >
  </div>
</template>
<script setup>
import { Button, ButtonClearInput, ButtonSearch } from "../../Shared";
import { ref } from "vue";
const props = defineProps({
  withSearchButton: {
    type: Boolean,
    default: false,
  },
  placeholder: {
    type: String,
    requred: false,
  },
});
const inputValue = ref("");
</script>
<style lang="scss">
@import "../../Shared/variables.scss";
@import "../../Shared/media.scss";
.search {
  display: flex;
  align-items: center;
  border: 1px solid $color-border;
  padding: 0px 16px 0px 6px;
  border-radius: 10px;
  height: 50px;

  transition: 0.3s;
  @include xs {
    border: none;
    border-bottom: 1px solid $color-border;
  }
  &:has(.search__field:focus) {
    border: 1px solid $color-brand;
    @include xs {
      border: none;
      border-bottom: 1px solid $color-brand;
    }
  }
  &:hover {
    border: 1px solid $color-brand;
    @include xs {
      border: none;
      border-bottom: 1px solid $color-brand;
    }
  }
  &__field {
    font-size: 16px;
    width: 100%;
    border: 0;

    &:focus {
      outline: none;
    }
  }
  &__clear-button {
    margin-right: 16px;
  }
}
</style>
