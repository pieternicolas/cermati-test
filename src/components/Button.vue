<template>
  <button class="btn">
    <slot></slot>
  </button>
</template>

<style lang="scss" scoped>
button {
  display: inline-block;
  font-weight: 400;
  color: #ffffff;
  text-align: center;
  vertical-align: middle;
  background-color: #1678C2;
  border: 1px solid #1678C2;
  padding: 0.375rem 0.75rem;
  font-size: 1rem;
  line-height: 1.5;
  border-radius: 0.25rem;
  transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out, border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;
  &:hover {
    cursor: pointer;
    color: #1678C2;
    background-color: #ffffff;
    border-color: #1678C2;
  }
}
</style>
