<template>
  <button class="button"><slot></slot></button>
</template>
<script setup></script>
<style lang="scss">
@import "../../variables.scss";
.button {
  padding: 8px 24px;
  font-size: 14px;
  font-family: 500;
  border: 1px solid $color-brand;
  border-radius: 8px;
  background-color: $color-white;
  transition: 0.3s;
  &:hover {
    color: $color-white;
    background-color: $color-brand;
  }
}
</style>
