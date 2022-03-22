<template>
<Navbar />
<router-view/>
</template>

<style lang="scss">

</style>
<script>
import Navbar from '@/components/Navbar'
export default {
   components: { Navbar },
}
</script>