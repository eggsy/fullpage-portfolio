<template>
  <div class="text-gray-700">
    <div class="flex justify-around mt-4">
      <div class="flex" v-for="(skill, index) in skills" :key="index">
        <img
          :src="skill.icon"
          :alt="skill.name"
          :title="skill.name"
        />
        <div class="card" :style="`background-color: ${calculateColor(skill.rate)}`">
          {{ skill.rate }}
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
  img {
    width: 42px;
    height: 42px;
    cursor: pointer;
    opacity: 0.75;
    transition: opacity 0.2s;
  }

  img:hover {
    opacity: 1;
  }

  img:not(:last-child) {
    margin-right: 6px;
  }

  .card {
    height: fit-content;
    color: white;
    padding: 0 0.25em;
    border-radius: 6px;
  }
</style>

<script>
  export default {
    data() {
      return {
        skills: [
          {
            name: "JavaScript",
            rate: 100,
            icon: require("../assets/icons/javascript.svg")
          },
          {
            name: "Node.js",
            rate: 95,
            icon: require("../assets/icons/nodejs.svg")
          },
          {
            name: "TypeScript",
            rate: 85,
            icon: require("../assets/icons/typescript.svg")
          },
          {
            name: "Nuxt.js",
            rate: 80,
            icon: require("../assets/icons/nuxtjs.svg")
          },
          {
            name: "Vue.js",
            rate: 70,
            icon: require("../assets/icons/vuejs.svg")
          }
        ]
      }
    },
    methods: {
      calculateColor(rate) {
        let color;

        if (rate > 85) color = "#27ae60";
        else if (rate > 70) color = "#16a085";
        else if (rate > 50) color = "#f39c12";
        else color = "#c0392b";

        return color;
      }
    }
  }
</script>
