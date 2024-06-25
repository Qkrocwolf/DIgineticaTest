<template>
  <div class="showcase">
    <CardOutOfStock :text="data" />
    <!--@vue-ignore-->
    <Card :text="data" v-for="card in 11"></Card>
  </div>
</template>
<script setup >
import { Card, CardOutOfStock } from "../../Features";
const data =
  "Полное название товара в несколько строк для вида с обрывом в конце Lorem ipsum dolor sit aaaaaaa";
</script>
<style lang="scss">
@import "../../Shared/media.scss";
@import "../../Shared/variables.scss";

.showcase {
  font-family: "PT Sans";
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 24px;
  @include md {
    grid-template-columns: repeat(3, 1fr);
  }
  @include ml {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>
