<script>
import Header from "@/components/HomePage/Header.vue";
import Main from "@/components/HomePage/Main.vue";
import Themes from "@/components/HomePage/Themes.vue";
import About from "@/components/HomePage/About.vue";
import Organizer from "@/components/HomePage/Organizer.vue";

export default {
  components: {Organizer, About, Themes, Main, Header},
  mounted() {
    this.$emit('updateResult', 0);
  }
}
</script>

<template>
  <Header/>
  <Main/>
  <About/>
  <Themes/>
  <Organizer/>
</template>

<style scoped>

</style>
