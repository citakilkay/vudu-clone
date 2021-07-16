<template>
  <div class="navbar">
    <nav class="navbar__body">
      <a class="navbar__toggler" v-on:click="openToggler">
        <span></span>
        <span></span>
        <span></span>
      </a>
      <div class="navbar__list">
        <a class="navbar__item -logo">
          <img src="https://www.vudu.com/content/images/logo.svg" alt=""/>
        </a>
        <a class="navbar__item">Movies</a>
        <a class="navbar__item">TV</a>
        <a class="navbar__item">Free</a>
        <a class="navbar__item">My Vudu</a>
      </div>
      <div class="navbar__list">
        <a class="navbar__item">Gift Cards</a>
        <a class="navbar__item">Redeem</a>
        <a class="navbar__item">Sign In</a>
        <a class="navbar__item fas fa-search"></a>
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  setup() {
    const openToggler = (e) => {
      const navbarItems = document.querySelectorAll(".navbar__item");
      if (e.target.classList.contains("-active")) {
        e.target.classList.remove("-active");
        navbarItems.forEach((navbarItem) => {
          navbarItem.classList.remove("-open");
        });
      } else {
        e.target.classList.add("-active");
        navbarItems.forEach((navbarItem) => {
          navbarItem.classList.add("-open");
        });
      }
    };
    return {
      openToggler,
    };
  },
};
</script>

<style lang='scss' scoped>
@import "../assets/scss/navbar";
</style>