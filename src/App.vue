<template>
  <v-app>
    <v-toolbar
      dark
      src="https://cdn.vuetifyjs.com/images/backgrounds/vbanner.jpg"
      max-height="60"
    >
      <v-toolbar-title>TouTube Curation</v-toolbar-title>
    </v-toolbar>

      <top />

    <v-toolbar
      dark
      src="https://cdn.vuetifyjs.com/images/backgrounds/vbanner.jpg"
    >
      <v-spacer />
      <p>&#64;QuestAcademia</p>
    </v-toolbar>
  </v-app>
</template>

<script>
  import Top from './components/Top.vue'
  export default {
    name: 'App',  // このソースの名前
    components: {
      Top,        // 呼び出すコンポーネント名
    }
  }
</script>

<style>

</style>