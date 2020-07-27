<template>
  <full-page :options="{ sectionSelector: '.container' }" ref="fullPage">
    <div class="container">
      <div class="text-gray-700 text-center">
        <div class="p-6">
          <img class="avatar w-32 h-32 mx-auto mb-2" draggable="false" src="/images/me2019.jpeg"
               alt="irl-image">

          <div class="text-center">
            <h2 class="text-lg">Abdulbaki "EGGSY" Dursun</h2>
            <div class="select-none cursor-pointer text-purple-500 mb-1" @click="randomRank">{{ rank }}</div>
            <Socials class="socials" />
          </div>
        </div>
      </div>

      <div class="select-none bottom-text text-center text-gray-700" @click="moveDown">
        <span>scroll down</span>
      </div>
    </div>

    <div class="container text-gray-700 max-w-md">
      <div class="text-left">
        <h1 class="text-lg title">Who am I?</h1>
        <p class="appear text-left">
          I am a Turkish student who is interested in programming and English literature. I
          am trying my best to bring useful and good ideas to the world, I program for fun, necessity or time-killing,
          I
          am
          actually trying to become an English teacher.
        </p>
      </div>

      <div class="select-none bottom-text text-center text-gray-700" @click="moveDown">
        <span>scroll down</span>
      </div>
    </div>

    <div class="container text-gray-700 max-w-md">
      <div class="text-left">
        <h1 class="text-lg title">What do I know so far?</h1>
        <p class="appear text-left">
          First of all, I am not the best, maybe not even "good", but I like what I do and I am happy with my current
          self; this doesn't mean that I'll stop learning new technologies and all, I'll definitely improve my skills
          in the future!
        </p>

        <h1 class="text-lg title mt-6">Skills</h1>
        <Skills />
      </div>

      <div class="select-none bottom-text text-center text-gray-700" @click="moveDown">
        <span>scroll down</span>
      </div>
    </div>

    <div class="container text-gray-700 max-w-md">
      <div class="text-left">
        <h1 class="text-lg title">Learn more about me!</h1>
        <p class="appear text-left">
          These are nothing compared to what I do on my main website! Please don't forget to check <a
          href="https://eggsy.xyz" class="underline" target="_blank">my website</a> to see my projects and learn more
          about me.
        </p>
      </div>

      <div class="select-none bottom-text text-center text-gray-700" @click="goTop">
        <span>go back to top</span>
      </div>
    </div>
  </full-page>
</template>

<style>
  .title {
    border-left: 4px solid purple;
    padding-left: 0.5em;
  }

  .container {
    margin: 0 auto;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
  }

  .bottom-text {
    cursor: pointer;
    position: absolute;
    bottom: 0.25em;
    left: 50%;
    transform: translateX(-50%);
    opacity: 0.75;
    transition: opacity 0.2s;
  }

  .bottom-text:hover {
    opacity: 1;
  }

  .avatar {
    border-radius: 100%;
    transition: border-radius 0.2s;
  }

  .avatar:hover {
    border-radius: 4px;
  }

  li {
    display: flex;
    justify-content: space-between;
  }

  @media only screen and (max-width: 1024px) {
    .container {
      padding: 0 2em;
    }

    .flex.mt-4 {
      text-align: center;
      justify-content: space-between;
    }

    .flex.mt-4 .flex {
      display: block;
    }

    .flex.mt-4 .flex img {
      margin: 0;
    }

    .flex.mt-4 .flex:not(:last-child) {
      margin-bottom: 0.5em;
    }
  }
</style>

<script>
  export default {
    data() {
      return {
        ranks: [
          "Gamer",
          "Student",
          "Turkish",
          "Vue Lover",
          "Programmer",
          "Still Young™",
          "Best Googler",
          "Sometimes Kid",
          "Netflix Lover",
          "Uses DuckDuckGo",
          "Backend Developer",
          "Not-Much-A-Person",
          "Stack Overflow FTW!",
          "Frontend Developer",
          "Full Stack Developer",
          "Prefers YouTube Music over Spotify",
        ],
        rank: "Full Stack Developer"
      };
    },
    methods: {
      moveDown() {
        this.$refs.fullPage.api.moveSectionDown();
      },
      goTop() {
        this.$refs.fullPage.api.moveTo(1);
      },
      randomRank() {
        this.rank = this.ranks.filter(r => r !== this.rank)[Math.floor(Math.random() * (this.ranks.length - 1))];
      }
    }
  };
</script>
