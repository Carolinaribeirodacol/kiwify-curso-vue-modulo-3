<template>
  <div class="navbar bg-neutral text-neutral-content">
    <div class="flex-1">
      <a class="btn btn-ghost text-xl">daisyUI</a>
    </div>

    <div class="flex-none">
      <ul class="menu menu-horizontal px-1">
        <li v-for="(menu, index) in menus" :key="index">
          <button @click="handlerRouteGoTo(menu.routeName)">{{ menu.label }}</button>
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup>
import { useRouter } from 'vue-router'

const router = useRouter()

const menus = [
  {
    label: 'Home',
    routeName: '/',
  },
  {
    label: 'About',
    routeName: '/about',
  },
]

function handlerRouteGoTo(routeName) {
  router.push(routeName)
}
</script>
