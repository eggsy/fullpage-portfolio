<template>
  <div class="text-gray-700">
    <div class="flex justify-center">
      <a v-for="(social, index) in socials" :key="index" :href="social.url" target="_blank">
        <img alt="icon" class="icon" :src="social.icon" />
      </a>
    </div>
  </div>
</template>

<style scoped>
img {
  width: 32px;
  height: 32px;
  cursor: pointer;
  opacity: 0.75;
  transition: opacity 0.2s;
}

img:hover {
  opacity: 1;
}

a:not(:last-child) {
  margin-right: 6px;
}
</style>

<script>
export default {
  data() {
    return {
      socials: [
        {
          url: "https://github.com/eggsydev/fullpage-portfolio",
          icon: require("../assets/icons/github.svg"),
        },
        {
          url: "https://twitter.com/eggsydev",
          icon: require("../assets/icons/twitter.svg"),
        },
        {
          url: "https://discord.eggsy.xyz",
          icon: require("../assets/icons/discord.svg"),
        },
      ],
    };
  },
  methods: {
    openInNew(key) {
      const url = this.socials[key].url;
      window.open(url, "_blank").focus();
    },
  },
};
</script>
