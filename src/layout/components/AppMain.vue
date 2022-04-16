<template>
  <section class="app-main">
    <Header />
    <Nav />
    <transition name="fade-transform" mode="out-in">
      <keep-alive>
        <router-view :key="key" />
      </keep-alive>
    </transition>
    <Footer />
    <el-backtop />
  </section>
</template>

<script>
import { Nav, Header, Footer } from "@/components";
export default {
  name: 'AppMain',
  components: {
    Nav,
    Header,
    Footer,
  },
  computed: {
    key() {
      return this.$route.path
    },
  }
}
</script>

<style lang="scss" scoped>
.app-main {
  width: 100%;
  position: relative;
}
</style>
