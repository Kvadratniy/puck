

<template>
  <div :class="$style.flex">
    <div :class="$style.btn">
      <UIButton
        color="primary"
        @click="click"
      >
        Primary
      </UIButton>
    </div>
    <div :class="$style.btn">
      <UIButton
        color="secondary"
      >
        Secondary
      </UIButton>
    </div>
    <div :class="$style.btn">
      <UIButton
        color="success"
      >
        Success
      </UIButton>
    </div>
    <div :class="$style.btn">
      <UIButton
        color="danger"
      >
        Danger
      </UIButton>
    </div>
    <div :class="$style.btn">
      <UIButton
        color="warning"
      >
        Warning
      </UIButton>
    </div>
    <div :class="$style.btn">
      <UIButton
        color="light"
      >
        Light
      </UIButton>
    </div>
    <div :class="$style.btn">
      <UIButton
        color="dark"
      >
        Dark
      </UIButton>
    </div>
  </div>
</template>


<script lang="ts">
import { defineComponent } from 'vue';
import UIButton from '@/components/UIButton.vue';

export default defineComponent({
  name: 'Home',
  components: {
    UIButton,
  },
  methods: {
    click(): void {
      debugger
    }
  }
});
</script>

<style module>
.container {
  width: 100%;
  height: 100vh;
}

.flex {
  display: flex;
  flex-direction: row;
  justify-content: center;
}

.btn {
  margin: 0 10px;
}

</style>