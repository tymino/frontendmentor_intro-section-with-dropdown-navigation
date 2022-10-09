<template>
  <button :class="`button button--${buttonType}`">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'my-button',
  props: {
    buttonType: {
      type: String,
      default: 'action',
    },
  },
};
</script>

<style lang="scss" scoped>
.button {
  border-radius: 14px;
  padding: 10px 20px;
  font-size: 1rem;
  text-transform: capitalize;
  cursor: pointer;

  &--action {
    border: 2px solid var(--color-black);
    background: var(--color-black);
    color: var(--color-white);

    &:hover {
      border: 2px solid var(--color-black);
      background: none;
      color: var(--color-black);
    }
  }

  &--primary {
    border: 2px solid var(--color-gray);
    background: var(--color-white);
    color: var(--color-gray);

    &:hover {
      border: 2px solid var(--color-black);
      background: none;
      color: var(--color-black);
    }
  }

  &--secondary {
    border: none;
    background: none;
    color: var(--color-gray);

    &:hover {
      color: var(--color-black);
    }
  }
}
</style>
