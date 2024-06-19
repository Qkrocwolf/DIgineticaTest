<template>
  <div class="price">
    <h3 class="price__label">Цена</h3>
    <div class="price__inputs">
      <label class="price__before">
        <input type="number" class="price__input" placeholder="5 500 &#8381;" />
      </label>
      <span class="price__dash">&mdash;</span>
      <label class="price__before">
        <input type="number" class="price__input" placeholder="5 500 &#8381;" />
      </label>
    </div>
  </div>
</template>
<style lang="scss">
@import "../../Shared/variables.scss";
.price {
  display: flex;
  flex-direction: column;
  gap: 16px;
  &__label {
    text-align: center;
    font-size: 16px;
    font-weight: 700;
    line-height: 20px;
  }
  &__inputs {
    display: flex;
    align-items: center;
    justify-content: space-around;
    position: relative;
    gap: 16px;
  }
  &__dash {
    opacity: 0.5;
  }
  &__input {
    width: 100%;
    padding: 10px 8px;
    border: 1px solid $color-border;
    border-radius: 4px;
    &:focus {
      outline: 1px solid $color-brand;
    }
  }
}
</style>
