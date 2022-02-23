<template>
  <div id="wrap">
    <TheHeader/>
    <div id="main-container" class="container main-container">
      <router-view/>
    </div>
    <TheFooter/>
  </div>
</template>
<script>
import TheHeader from '@/components/layouts/TheHeader'
import TheFooter from '@/components/layouts/TheFooter'
export default {
  name: 'App',
  components: {
    TheHeader,
    TheFooter
  }

}
</script>

<style lang="scss">
$icon-font-path: "~bootstrap-sass/assets/fonts/bootstrap/";
$fa-font-path: "~font-awesome/fonts/";
@import "~bootstrap-sass/assets/stylesheets/_bootstrap";
@import "~font-awesome/scss/font-awesome";
</style>