<script setup>

const route = useRoute()
const colorMode = useColorMode()
const isDark = computed({
  get() {
    return colorMode.value === 'dark'
  },
  set() {
    colorMode.preference = colorMode.value === 'dark' ? 'light' : 'dark'
  },
})
const links = [[
  { label: 'TodayRandTokyo', to: '/' },
  { label: "Home", to: '/', icon: 'i-heroicons-home-16-solid' },
  { label: "About", to: '/about' },
  { label: "Destination", to: '/destination' },
  { label: "Package", to: '/package' },
  { label: "Contact", to: '/contact' },
],
[
  { label: "SignUp", to: '/signup' },
  { label: "Login", to: '/login' },
  {
    icon: isDark ? 'i-heroicons-moon-20-solid' : 'i-heroicons-sun-20-solid',
    click: () => colorMode.preference = isDark.value == true ? 'light' : 'dark'
  }
]
]

const handler = () => {
  console.log('hi');
}
</script>

<template>
  <div>

    <UHorizontalNavigation :links="links" class="border-b border-gray-200 dark:border-gray-800" />
    <div class="h-screen items-center justify-center">
      <div class="">
        <UButton @click="handler">Find out Today random place in Tokyo!</UButton>
        <UButton @click="handler">Find out Today random place in Tokyo!</UButton>
      </div>

    </div>
  </div>
</template>
