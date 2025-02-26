<script setup>
import Banner from './components/BannerComponent.vue'

// import { RouterLink, RouterView } from 'vue-router'
// import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <div id="content-image-wrap">
    <div id="banner-content-wrap">
      <Banner text="mary plastic " />
      <Banner text="plastic mary " :styled_el="1" />
      <Banner text="mary plastic " />
      <Banner text="plastic mary " :styled_el="10" />
      <div id="content-wrapper">
        <RouterView />
        <div id="footer-wrapper">
          <img class="footer" src="/house-footer.png" />
        </div>
      </div>
    </div>
    <img id="right-sticky-photo" src="/clock-amp.png" />
  </div>
</template>

<style scoped>
#banner-content-wrap {
  padding-top: 20px;
  margin-left: 10px;
  margin-right: 10px;
  border-left: thick double var(--maroon);
  border-right: thin solid var(--maroon);
  overflow: auto;
  height: 100vh;
}

#content-wrapper {
  padding: 10px;
  padding-top: 30px;
  overflow: auto;
}

#content-image-wrap {
  display: flex;
  justify-content: space-between;
  position: fixed;
  left: 0px;
}

#right-sticky-photo {
  height: 100vh;
  right: 0px;
  top: 0px;
}

#footer-wrapper {
  width: 100%;
  display: block;
  /* position: absolute; */
  bottom: 10px;
}

.footer {
  padding-top: 50px;
  width: clamp(300px, 30%, 2000px);
  display: block;
  left: 0;
  right: 0;
  margin: auto;
}
</style>
