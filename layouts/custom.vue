<template>
    <div id="app">
      <HeaderWeb />
    <Nuxt />
    <FooterWeb />
    </div>
  </template>
  <script>
    import Header from "@/components/HeaderWeb.vue"
    import Footer from "@/components/FooterWeb.vue"
    export default {
    layouts: {
    Header,
    Footer
    }
    }
  </script>
  