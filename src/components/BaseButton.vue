<template>
  <button :class="styling">{{ text }}</button>
</template>

<script>
export default {
  props: {
    text: {
      type: String,
      required: true,
    },
    variant: {
      type: String,
      default: "primary",
      validator(propValue) {
        return ["primary", "secondary"].includes(propValue);
      },
    },
  },
  computed: {
    styling() {
      return ["btn", `btn--${this.variant}`];
    },
  },
};
</script>

<style scoped>
.btn {
  border: 3px solid transparent;
  border-radius: 3px;
  padding: 5px;
}

.btn--primary {
  border-color: var(--primary-dark);
  background-color: var(--primary);
  color: #fff;
}

.btn--secondary {
  border-color: var(--primary);
  background-color: transparent;
  color: var(--primary);
}
</style>
