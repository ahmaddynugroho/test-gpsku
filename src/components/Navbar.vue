<template>
  <div class="nav-container">
    <!-- LOGO -->
    <div class="nav-logo">GPSKU</div>

    <!-- LEFT MENUS -->
    <div class="flex">
      <Dropdown
        v-for="(menu, i) in dropdownMenus"
        :key="i"
        class="mr-2 px-2 py-1 rounded hover:bg-gray-200"
        :title="menu.title"
      >
        <ul class="bg-white rounded shadow">
          <li v-for="(sub, j) in menu.subMenu" :key="j">
            <Button class="nav-button" :title="sub.title" />
          </li>
        </ul>
      </Dropdown>
    </div>

    <!-- RIGHT MENUS -->
    <div class="flex">
      <Dropdown
        v-for="(menu, i) in dropdownMenus2"
        :key="i"
        class="mr-2 px-2 py-1 rounded hover:bg-gray-200"
        :faIcon="menu.faIcon"
        :title="menu.title"
      >
        <template v-if="i === 2" v-slot:prefix>
          <i class="fas fa-circle fa-2x"></i>
        </template>
        <ul class="bg-white rounded shadow">
          <li v-for="(sub, j) in menu.subMenu" :key="j">
            <Button class="nav-button" :title="sub.title" />
          </li>
        </ul>
      </Dropdown>
    </div>
  </div>
</template>

<script>
import Dropdown from '../components/UI/Dropdown'
import Button from '../components/UI/Button'

export default {
  components: {
    Dropdown,
    Button,
  },
  data() {
    return {
      dropdownMenus: [
        {
          title: 'Master',
          subMenu: [
            { title: 'Sub Menu 1' },
            { title: 'Sub Menu 2' },
            { title: 'Sub Menu 3' },
            { title: 'Sub Menu 4' },
          ],
        },
        {
          title: 'Report',
          subMenu: [
            { title: 'Sub Menu 1' },
            { title: 'Sub Menu 2' },
            { title: 'Sub Menu 3' },
            { title: 'Sub Menu 4' },
          ],
        },
        {
          title: 'Billing',
          subMenu: [
            { title: 'Sub Menu 1' },
            { title: 'Sub Menu 2' },
            { title: 'Sub Menu 3' },
            { title: 'Sub Menu 4' },
          ],
        },
        {
          title: 'HRD',
          subMenu: [
            { title: 'Sub Menu 1' },
            { title: 'Sub Menu 2' },
            { title: 'Sub Menu 3' },
            { title: 'Sub Menu 4' },
          ],
        },
      ],
      dropdownMenus2: [
        {
          faIcon: 'fas fa-pencil-ruler',
          subMenu: [{ title: 'sub 1' }, { title: 'sub 2' }],
        },
        {
          faIcon: 'fas fa-language',
          subMenu: [{ title: 'sub 1' }, { title: 'sub 2' }],
        },
        {
          title: 'Administrator',
          subMenu: [{ title: 'sub 1' }, { title: 'sub 2' }],
        },
      ],
    }
  },
}
</script>

<style scoped>
.nav-container {
  @apply container mx-auto flex justify-between relative;
}
.nav-logo {
  @apply absolute py-1 w-full text-center;
}
.nav-button {
  @apply w-full px-4 py-2 hover:bg-gray-200 text-left;
}
</style>
