<template>
  <div>
    <Nuxt />

    <ThemeSwitcher />
  </div>
</template>

<style>
  body, html {
    height: 100vh;
    width: 100vw;
    min-height: 100vh;
    transition: background-color 0.2s;
  }

  html {
    font-family: "lexend Deca", sans-serif;
    font-size: 16px;
    word-spacing: 1px;
    -ms-text-size-adjust: 100%;
    -webkit-text-size-adjust: 100%;
    -moz-osx-font-smoothing: grayscale;
    -webkit-font-smoothing: antialiased;
    box-sizing: border-box;
  }

  *,
  *::before,
  *::after {
    box-sizing: border-box;
    margin: 0;
  }

  /* Transitions */
  .icon {
    transition: background-color 0.2s;
  }

  /* Dark mode settings */
  .dark-mode body {
    background-color: #131516;
    color: #F5F5F5;
  }

  .dark-mode h1, .dark-mode h2 {
    color: #F5F5F5;
  }

  .dark-mode .text-gray-700 {
    color: #b0a99f;
  }

  .dark-mode .icon {
    filter: contrast(0);
  }

  .dark-mode .switcher {
    background-color: #2e2e2e;
  }
</style>
<script>
  import ThemeSwitcher from "../components/ThemeSwitcher";

  export default {
    components: { ThemeSwitcher }
  };
</script>
