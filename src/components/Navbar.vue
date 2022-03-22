<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
  <router-link class="navbar-brand" :to="{name: 'Home'}">Navbar</router-link>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNavDropdown" aria-controls="navbarNavDropdown" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>
  <div class="collapse navbar-collapse" id="navbarNavDropdown">
    <ul class="navbar-nav">
      <li class="nav-item active">
        <router-link class="nav-link"  :to="{name: 'Home'}">Home</router-link>
      </li>
      <li class="nav-item">
        <router-link class="nav-link"  :to="{name: 'About'}">About</router-link>
      </li>
      <li class="nav-item">
        <router-link class="nav-link"  :to="{name: 'Services'}">Services</router-link>
      </li>
       <li class="nav-item">
        <router-link class="nav-link"  :to="{name: 'Mechanics'}">Mechanics</router-link>
      </li>
      <li class="nav-item">
     <router-link class="nav-link" :to="{name: 'Dashboard'}">Dashboard</router-link>
     </li>
     <li class="nav-item">
          <router-link class="nav-link" :to="{name: 'Login'}">Sign Out</router-link>
          </li>
    </ul>
  </div>
</nav>
</template>

<script>
export default {

}
</script>

<style>

</style>