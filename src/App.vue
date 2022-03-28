<template>
<Navbar />
<router-view/>
</template>

<script>
import Navbar from '@/components/Navbar'
export default {
   components: { Navbar },
}
</script>

<style lang="scss">
//text color
$primaryText : #021a49;
$secondaryText : #171D24;
$tertiaryText : #fff;
//color theme
$primaryBg : #00509d;
$secondaryBg : #003f88;
$tertiaryBg : #00296b;
//fonts
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,300;0,400;0,900;1,200;1,300&family=Rubik:ital,wght@0,300;0,400;0,500;0,600;0,700;1,300;1,400&display=swap');
$primaryFont: 'Poppins', sans-serif;
$secondaryFont: 'Rubik', sans-serif;

a{
  text-decoration: none !important;
}
</style>