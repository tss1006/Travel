<template>
   <div>
     <home-header></home-header>
     <home-swipper></home-swipper>
     <home-icon></home-icon>
   </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwipper from './components/swipper'
import HomeIcon from './components/Icon'
export default{
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwipper,
    HomeIcon
  }
}
</script>

<style>
</style>
