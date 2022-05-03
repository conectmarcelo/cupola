<template>
  <v-app style="background-color: #F3F6F7">
    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: "App",

  data: () => ({
    //
  }),
};
</script>

<style>
@font-face {
  font-family: "DMSans";
  src: local("DMSans"),
    url(./fonts/DMSans/DMSans-Regular.ttf) format("truetype");
}
</style>