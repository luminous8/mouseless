<template>
  <button
    class="button"
    :class="{
      'is-yellow': isYellow,
      'is-red': isRed,
      'is-red-text': isRedText,
      'is-grey-text': isGreyText,
    }"
    type="button"
  >
    <icon class="button__icon" :name="icon" v-if="icon" />
    <span class="button__content" v-if="$scopedSlots.default">
      <slot />
    </span>
  </button>
</template>

<script>
import Icon from '@/components/Icon'

export default {
  name: 'Btn',

  components: {
    Icon,
  },

  props: {
    icon: {
      default: null,
      type: String,
    },

    isYellow: {
      default: false,
      type: Boolean,
    },

    isRed: {
      default: false,
      type: Boolean,
    },

    isRedText: {
      default: false,
      type: Boolean,
    },

    isGreyText: {
      default: false,
      type: Boolean,
    },
  },
}
</script>

<style lang="scss" src="./style.scss" scoped></style>
