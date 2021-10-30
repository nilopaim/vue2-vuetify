<template>
  <v-app>
    <v-app-bar app color="primary" dark data-wails-drag>
      <div class="d-flex align-center">
        <v-img
          alt="Pcast Logo"
          class="shrink mr-2"
          contain
          src="./assets/logo.png"
          transition="scale-transition"
          width="60"
        />

        <h2 class="ml-3">PCast Transmitter</h2>
      </div>

      <v-spacer />
      <v-icon color="white" @click="onclickMinimise" class="ml-2"
        >mdi-window-minimize</v-icon
      >

      <v-icon color="white" @click="onclickMaximise" class="ml-2"
        >mdi-window-maximize</v-icon
      >

      <v-icon color="white" @click="onclickQuit" class="ml-2"
        >mdi-window-close</v-icon
      >
    </v-app-bar>

    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: "App",

  methods: {
    onclickMinimise() {
      window.runtime.WindowMinimise();
    },

    onclickMaximise() {
      window.runtime.WindowMaximise();
    },

    onclickQuit() {
      window.runtime.Quit();
    },
  },
};
</script>

<style>
html {
  width: 100%;
  height: 100%;
  overflow: auto;
}
</style>
