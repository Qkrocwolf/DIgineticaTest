<template>
  <button class="clear-input-button">
    <img
      src="../../Assets/autocompleteOff.svg"
      alt="autocomplete"
      onmouseenter="src='src/Shared/Assets/autocompleteHover.svg'"
      onmouseleave="src='src/Shared/Assets/autocompleteOff.svg'"
    />
  </button>
</template>

<style lang="scss">
.clear-input-button {
  background-color: transparent;
  border: none;
}
</style>
