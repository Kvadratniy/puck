<template>
  <button
    :class="{
      [$style.base]: true,
      [$style[color]]: true,
    }"
  >
    <slot/>
  </button>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'UiButton',
  props: {
    color: {
      type: String,
      default: 'primary',
      validate: (value: string) => [
        'primary',
        'secondary',
        'success',
        'danger',
        'warning',
        'light',
        'dark'
      ].includes(value),
    }
  },

  computed: {
    classes(): { [x: number]: boolean } {
      const {
        $style,
        color,
      } = this;

      return {
        [$style[color]]: true,
      };
    }
  },
});
</script>

<style module lang="less">
.base {
  border-radius: 6px;
  border: none;
  font-size: 0.9rem;
  color: white;
  padding: 10px 25px;
  cursor: pointer;
}

.base:focus {
  outline: none;
}

.primary {
  background-color: #007bff;
  color: white;
  &:hover {
    background-color: #006fe6;
  }
}

.secondary {
  background-color: #6c757d;
  color: white;
  &:hover {
    background-color: #65686b;
  }
}

.success {
  background-color: #28a745;
  color: white;
  &:hover {
    background-color: #259940;
  }
}

.danger {
  background-color: #dc3545;
  color: white;
  &:hover {
    background-color: #ca2b3b;
  }
}

.warning {
  background-color: #ffc107;
  color: #000000;
  &:hover {
    background-color: #e9b007;
  }
}

.light {
  background-color: #f8f9fa;
  color: #000000;
  &:hover {
    background-color: #e8e8e9;
  }
}

.dark {
  background-color: #343a40;
  color: #ffffff;
  &:hover {
    background-color: #282d31;
  }
}
</style>
