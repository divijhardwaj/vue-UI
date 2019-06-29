<template>
  <div class="main-container">
    <div class="nav-container">
      <input class="toggle-sidenav" @click="toggle=true" type="button">
    </div>
    <div class="sidenav-container">
      <SideBar :sidenav="toggle" @closeSidenav="toggle = false"/>
    </div>
    <div class="content-container"></div>
  </div>
</template>

<script>
import SideBar from "../components/SideBar";
import Component from "vue-class-component";

export default {
  components: {
    SideBar
  },
  data: () => ({
    toggle: false
  })
};
</script>

<style lang="scss" scoped>
.main-container {
  width: 100%;
  height: 100vh;

  display: grid;
  grid-template-areas:
    "side-nav nav"
    "side-nav cont";
  grid-template-columns: 80px 1fr;
  grid-template-rows: 80px 10fr;

  .nav-container {
    grid-area: nav;
    position: fixed;
    height: 80px;
    width: 100%;
    margin-left: 80px;
    background-color: white;
    box-shadow: 0px 2px 15px -15px black;

    .toggle-sidenav {
      width: 50px;
      height: 50px;
      background-color: black;
      border: none;
    }
  }
  .sidenav-container {
    grid-area: side-nav;
    position: fixed;
    width: 80px;
    height: 100vh;
    // background-color: blue;
  }
  .content-container {
    grid-area: cont;
    background-color: #f8f9fb;
    height: 1000px;
  }
}

@media only screen and (max-width: 600px) {
  .main-container {
    grid-template-areas:
      "nav"
      "cont";
    grid-template-columns: 1fr;
    .sidenav-container {
      display: none;
    }
    .nav-container {
      margin-left: 0%;
    }
  }
}
</style>
 

