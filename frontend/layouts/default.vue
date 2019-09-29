<template>
  <div id="app">
    <v-app>
      <v-toolbar>
        <n-link id="top" to="/">Nuxt-Rails-Sample</n-link>
      </v-toolbar>
      <v-content>
        <v-container fluid>
          <nuxt />
        </v-container>
      </v-content>
    </v-app>
  </div>
</template>

<style lang="scss">
body {
  .v-toolbar {
    &__content {
      padding: 0 2rem;
      a {
        text-decoration: none;
        color: #616161;
        font-weight: bold;
        font-size: 1.5rem;
      }
    }
  }
  .container {
    display: flex;
    min-height: 100vh;
    padding: 2rem;
  }
}
</style>
