<template>
  <b-navbar toggleable="md" type="dark" variant="info">
    <b-navbar-toggle target="nav_collapse"></b-navbar-toggle>
    <b-navbar-brand href="#">Wikipedia on Vue</b-navbar-brand>
    <b-collapse is-nav id="nav_collapse">
      <!-- Right aligned nav items -->
      <b-navbar-nav class="ml-auto">
        <b-nav-item href="#">Dashboard</b-nav-item>
        <b-nav-item href="#">History</b-nav-item>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</template>

<style scoped src="./navbar.css"></style>
<script>
  export default {
  }
</script>
