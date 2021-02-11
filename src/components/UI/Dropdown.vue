<template>
  <div
    class="cursor-pointer relative flex items-center"
    @mouseenter="toggleSub($event.target.childNodes[3])"
    @mouseleave="toggleSub($event.target.childNodes[3])"
  >
    <div class="inline">
      <slot name="prefix"></slot>
      <i :class="faIcon"></i>
    </div>
    <span class="mx-1">{{ title }}</span>
    <i class="fas fa-chevron-down fa-xs"></i>
    <div
      class="hidden absolute left-0 top-0 z-10 min-w-full bg-white whitespace-nowrap transform translate-y-10"
    >
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    faIcon: String,
    title: String,
  },
  methods: {
    toggleSub(e) {
      e.classList.toggle('hidden')
      ;['transform', 'rotate-180'].forEach((c) => {
        e.previousElementSibling.classList.toggle(c)
      })
    },
  },
}
</script>
