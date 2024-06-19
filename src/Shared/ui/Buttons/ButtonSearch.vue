<template>
  <button class="button-search">
    <img
      class="button-search__img"
      src="../../Assets/search.svg"
      alt="search"
    />
  </button>
</template>
<style lang="scss">
@import "../../variables.scss";
.button-search {
  background-color: transparent;
  padding: 10px;
  border: none;
  outline: none;
  transition: 0.3s;
  border-radius: 8px;
  &:hover {
    background-color: $color-brand;
  }
}
</style>
