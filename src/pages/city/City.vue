<template>
    <div>
        <city-header></city-header>
        <city-search :city='cities'></city-search>
        <city-list :city='cities' :hotcity="hotCities" :alphabet="alphabet"></city-list>
        <city-alphabet :city='cities' @change='changeHandle'></city-alphabet>
    </div>

</template>

<script>
    import CityHeader from './components/Header'
    import CitySearch from './components/Search'
    import CityList from './components/List'
    import CityAlphabet from './components/Alphabet'
    import axios from 'axios'
    export default {
        name: 'City',
        components: {
            CityHeader,
            CitySearch,
            CityList,
            CityAlphabet
        },
        data(){
           return{
               cities:{},
               hotCities:[],
               alphabet:""
           }
        },
        methods:{
          getCityInfo(){
              axios.get('/static/mock/city.json').then(this.handleGetCityInfoSuccess);
          },
          handleGetCityInfoSuccess(res){
              res=res.data;
            if(res.ret&&res.data){
                const data=res.data;
                this.cities=data.cities;
                this.hotCities=data.hotCities;
            }
          },
          changeHandle(res){
            this.alphabet=res;
          }
        },
        mounted(){
            this.getCityInfo();
        }
    }
</script>

<style scoped>
</style>