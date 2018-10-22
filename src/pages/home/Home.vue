<template>
   <div>
     <home-header></home-header>
     <home-swipper></home-swipper>
   </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwipper from './components/swipper'
export default{
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwipper
  }
}
</script>

<style>
</style>
