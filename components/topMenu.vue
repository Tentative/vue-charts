<template>
  <div>
    <b-navbar toggleable="lg" type="dark" variant="info" class="ml-auto">
      <b-navbar-brand href="#">NavBar</b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <b-nav-item href="#">Chart 1</b-nav-item>
          <b-nav-item href="#">Chart 2</b-nav-item>
          <b-nav-item href="#">Chart 3</b-nav-item>
          <b-nav-item href="#" disabled>Disabled</b-nav-item>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>

<script>
export default {}
</script>

<style></style>
