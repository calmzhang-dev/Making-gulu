<template>
  <div class="wrapper">
    <input type="text" :value="value" :disabled="disabled" :readonly="readonly" :class="{'error': error}"
           @change="$emit('change', $event.target.value)"
           @input="$emit('input', $event.target.value)"
           @focus="$emit('focus', $event.target.value)"
           @blur="$emit('blur', $event.target.value)"
    >
    <template v-if="error">
      <g-icon name="error" class="icon-error"></g-icon>
      <span class="errorMessage">{{ error }}</span>
    </template>
  </div>
</template>

<script>
import Icon from './icon'

export default {
  name: "g-input",
  components: {
    'g-icon': Icon
  },
  props: {
    value: {
      type: String,
      default: ''
    },
    disabled: {
      type: Boolean,
      default: false
    },
    readonly: {
      type: Boolean,
      default: false
    },
    // 错误信息
    error: {
      type: String
    }
  }
}
</script>

<style lang="scss" scoped>
@import "common/css/var";

.wrapper {
  display: inline-flex;
  align-items: center;
  font-size: $font-size;

  * {
    margin-right: 0.5em;

    &:last-child {
      margin-right: 0;
    }
  }

  > input {
    height: $input-height;
    border: 1px solid $border-color;
    border-radius: $border-radius;
    padding: 0 8px;
    font-size: inherit;

    &:hover {
      border-color: $border-color-hover;
    }

    &:focus {
      box-shadow: inset 0 1px 3px $box-shadow-color;
      outline: none;
    }

    &[disabled] {
      border-color: #bbb;
      color: #bbb;
      cursor: not-allowed;
    }

    &.error {
      border-color: $red;
    }
  }

  .icon-error {
    fill: $red;
  }

  .errorMessage {
    color: $red;
  }
}
</style>
