<template>
  <div class="relative">
    <span v-if="faIcon" class="absolute bottom-5 left-4" :class="faIcon"></span>
    <input
      class="my-2 py-2 rounded-md bg-gray-100 w-full"
      :class="{
        'pl-12': faIcon,
        'pl-4': !faIcon,
        'pr-12': faIconButton,
        'pr-4': !faIconButton,
      }"
      :type="type"
      :placeholder="placeholder"
      :value="modelValue"
      @input="$emit('update:modelValue', $event.target.value)"
      @focus="handleFocus($event.target)"
      @blur="handleFocus($event.target)"
    />
    <button
      v-if="faIconButton"
      class="absolute bottom-5 right-4"
      :class="faIconButton"
      @click="$emit('faIconButtonClick', $event.target.previousElementSibling)"
    ></button>
  </div>
</template>

<script>
export default {
  props: {
    modelValue: String,
    faIcon: String,
    faIconOnFocus: String,
    faIconButton: String,
    placeholder: String,
    focus: {
      type: String,
      default: 'outline-none ring-1 ring-blue-500',
    },
    type: {
      type: String,
      default: 'text',
    },
  },
  emits: ['faIconButtonClick', 'update:modelValue'],
  methods: {
    handleFocus(e) {
      const leftIcon = e.previousElementSibling

      const classesFocus = this.focus.split(' ')
      const classesFaIcon = this.faIconOnFocus.split(' ')

      classesFocus.forEach((c) => e.classList.toggle(c))
      classesFaIcon.forEach((c) => leftIcon.classList.toggle(c))
    },
  },
}
</script>
