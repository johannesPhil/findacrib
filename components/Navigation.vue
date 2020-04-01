<template>
  <div class="transparent">
    <b-row fluid>
      <b-navbar fixed="true" toggleable="lg" type="light" variant="faded">
        <b-navbar-toggle target="nav-text-collapse"></b-navbar-toggle>
        <b-navbar-brand>BootstrapVue</b-navbar-brand>
        <b-collapse id="nav-text-collapse" is-nav>
          <b-navbar-nav>
            <b-nav-item to="/" exact-active-class="active">Home</b-nav-item>
            <b-nav-item active-class="active">Accomodations</b-nav-item>
            <b-nav-item active-class="active">Sign In</b-nav-item>
            <b-nav-item to="/register" active-class="active">Sign Up</b-nav-item>
          </b-navbar-nav>
        </b-collapse>
      </b-navbar>
    </b-row>
  </div>
</template>

<style scoped>
.transparent {
  height: fit-content;
}
.navbar-light[data-v-1ab769ff] {
  width: 100%;
  height: auto;
  z-index: 2;
  background-color: transparent;
}
.navbar-light .navbar-nav .show > .nav-link,
.navbar-light .navbar-nav .active > .nav-link,
.navbar-light .navbar-nav .nav-link.show,
.navbar-light .navbar-nav .nav-link.active {
  background-color: transparent;
  padding: 0.5rem rem;
  color: #fff;
}
.nav-link {
  padding-top: 2rem;
}
.navbar-light .navbar-nav .nav-link:hover,
.navbar-light .navbar-nav .nav-link:focus,
.navbar-light .navbar-nav .nav-link.active {
  border-bottom: solid 2px #fff;
  color: #fff;
}
.nav-item {
  padding: 0 2rem;
}
.navbar-light,
.navbar-nav,
.nav-link:hover {
  color: #495057;
}
</style>
