<template>
  <nav class="navbar sticky-top navbar-expand-lg navbar-light p-0">
  <router-link class="navbar-brand" :to="{name: 'Home'}"><img class="logo" src="https://i.ibb.co/HCTkcym/Mobi-Mech-1.png" alt="logo"></router-link>
  <button class="navbar-toggler me-1" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavDropdown" aria-controls="navbarNavDropdown" aria-expanded="false" aria-label="Toggle navigation">
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
        <router-link class="nav-link"  :to="{name: 'BookAService'}">Book A Service</router-link>
      </li>
       <li class="nav-item dropdown">
          <a class="nav-link dropdown-toggle" href="#" id="navbarDropdownMenuLink" role="button" data-bs-toggle="dropdown" aria-expanded="false">
            Profile
          </a>
          <ul class="dropdown-menu" aria-labelledby="navbarDropdownMenuLink">
            <router-link class="nav-link"  :to="{name: 'Dashboard'}">Dashboard</router-link>
         <li> <router-link class="nav-link" :to="{name: 'Login'}">Sign in</router-link></li>
           <li> <router-link class="nav-link" :to="{name: 'Login'}">Sign out</router-link></li>
           <li> <router-link class="nav-link" :to="{name: 'Register'}">Register</router-link></li>

          </ul>
        </li>
       <li class="nav-item">
        <router-link class="nav-link"  :to="{name: 'Mechanics'}">Mechanics</router-link>
      </li>
       
    </ul>
  </div>
</nav>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
//text color
$primaryText: #021a49;
$secondaryText: #171D24;
$tertiaryText: #fff;
//color theme
$primaryBg: #00509d;
$secondaryBg: #003f88;
$tertiaryBg: #00296b;
//fonts
$primaryFont: 'Poppins', sans-serif;
$secondaryFont: 'Rubik', sans-serif;
//styling
.navbar{
  background-color: $primaryBg !important;
  color: $tertiaryText !important;
}
nav{
  box-shadow: 0 2px 4px 0 rgba(0,0,0,.2);
}
.nav-link{
 letter-spacing: 1px !important;
  color: $tertiaryText !important;
  font-family: $primaryFont;
  margin-left: 30px;
  border-radius: 12px;
}
 .navbar-brand{
  color: $tertiaryText !important;
  font-family: $primaryFont;
}
.logo{
  height: 80px;
  // width: 136px;
  object-fit: cover;
  margin-left: 20px;
}
.navbar-nav{
position: fixed;
top: 20px;
right: 30px;
}
.nav-link:hover{
background-color: $secondaryBg;
border-radius: 12px;
transition: 0.4s ease all;
}
.dropdown-menu{
  background-color: $primaryBg;
}

</style>