<template>
  <div class>
    <nav class="navbar is-spaced">
      <div class="navbar-brand">
        <a class="navbar-item" href="/">
          <img class="is-128x128" src="../../public/img/logo.png" />
        </a>
        <!--
    Using the v-on: directive to listen for the click event and toggle the data property showNav. Also, using the v-bind: directive to reactively update the class attribute 'is-active' based on the showNav property.
        -->
        <div class="navbar-burger" @click="showNav = !showNav" :class="{ 'is-active': showNav }">
          <span></span>
          <span></span>
          <span></span>
        </div>
      </div>
      <!--
    Using the v-bind: directive to reactively update the class attribute 'is-active' based on the showNav property.
      -->
      <div class="navbar-menu" :class="{ 'is-active is-mobile': showNav }">
        <div class="navbar-end">
          <a class="navbar-item" href="https://github.com/jurra/demo-alion">
            <span>Github Repo</span>
            <span class="icon has-text-grey">
              <i class="fab fa-github"></i>
            </span>
          </a>
        </div>
      </div>
    </nav>
  </div>
</template>
<script>
export default {
  data() {
    return {
      showNav: false
    };
  }
};
</script>
<style scoped>
.is-mobile {
  position: absolute;
  width: 60%;
  right: 0px;
  top: 4.2rem;
}
</style>


