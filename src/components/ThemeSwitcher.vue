<template>
  <div
    class="switcher absolute right-0 bottom-0 p-2 rounded cursor-pointer m-8"
    title="Click here to switch theme"
    @click="switchTheme"
  >
    <img
      alt="theme-switcher"
      class="w-6 h-6 icon"
      :src="$colorMode.value === 'dark' ? require('../assets/icons/themeSwitcher/moon.svg') : require('../assets/icons/themeSwitcher/sun.svg')"
    />
  </div>
</template>

<style>
.switcher {
  background-color: #8c939f;
}

.switcher {
  opacity: 0.75;
  transition: opacity 0.2s;
}

.switcher:hover {
  opacity: 1;
}
</style>

<script>
export default {
  methods: {
    switchTheme() {
      if (this.$colorMode.value === "dark")
        return (this.$colorMode.value = "light");
      else return (this.$colorMode.value = "dark");
    },
  },
};
</script>
