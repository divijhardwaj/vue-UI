<template>
  <div class="side-nav" :class="{'toggle-sidenav': sidenav}">
    <div class="company-name">
      <div class="nav-list brand">
        <div class="list-img"></div>
        <div class="list-label" :class="{'toggle-list-label': sidenav}">
          <p>hello</p>
        </div>
      </div>
    </div>
    <div class="nav-list" v-for="(item,index) in items" :key="index">
      <div class="list-img"></div>
      <div class="list-label" :class="{'toggle-list-label': sidenav}">
        <p>{{sidenav}}</p>
      </div>
    </div>
    <div class="close-sidenav" v-if="sidenav===true" @click="$emit('closeSidenav')"></div>
  </div>
</template>

<script>
export default {
  data: () => ({
    items: {
      0: "DashBoard",
      1: "Profile",
      2: "EMI",
      3: "Wallet",
      4: "Logout"
    }
  }),
  props: {
    sidenav: false
  }
};
</script>
<style lang="scss">
.side-nav {
  height: 100%;
  width: 80px;
  //   width: 200px;
  background-color: #1458ea;
  color: white;
  display: flex;
  flex-wrap: nowrap;
  flex-direction: column;
  position: relative;
  transition: 0.2s all ease;

  &.toggle-sidenav {
    width: 300px;
  }

  .company-name {
    height: 120px;
    background-color: lightblue;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .close-sidenav {
    align-self: right;
    width: 10px;
    height: 10px;
    background-color: black;
  }
  .nav-list {
    width: 100%;
    height: 60px;
    margin-top: 10px;

    background-color: lightblue;
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
    align-items: center;
    justify-content: center;

    &.brand {
      .list-img {
        // scale up
        width: 40px;
        height: 40px;
      }
      .list-label {
        // scale up
      }
    }

    .list-img {
      display: flex;
      width: 30px;
      height: 30px;
      border: 1px solid black;
      align-items: center;
      justify-content: left;
    }
    .list-label {
      display: none;
      flex: 2;
      height: 30px;
      border: 1px solid black;
      align-items: center;
      justiy-content: left;

      &.toggle-list-label {
        display: flex;
      }
    }
  }
}
</style>
