<template>
    <div>
        <banner></banner>
        <detail-header></detail-header>
        <div class="container"></div>
    </div>

</template>

<script>
    import Banner from './components/Banner'
    import DetailHeader from './components/Header'
    export default {
        name: 'Detail',
        components: {
            Banner,
            DetailHeader
        }
    }
</script>
<style scoped>
  .container{
      height: 50rem;
  }
</style>