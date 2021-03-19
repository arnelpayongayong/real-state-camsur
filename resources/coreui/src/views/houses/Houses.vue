<template src="../../templates/house/mainhouse.html">

</template>

<script>
import Navbar from '../../custom/Navbar.vue'
import Footer from '../../custom/Footer'
export default {
    components : {Navbar,Footer},
    data(){
        return{
            houses : [],
            houseAndLot : [],
            condominium : [],
            lot : [],
            land : []
        }
    },
    created(){
        this.getHouses()
    },
    methods: {
        getHouses(){
            this.axios.get('house/index')
            .then(response => {
                this.houseAndLot = Object.assign(this.houseAndLot,response.data.houses.filter(house => house.listing_type == 'House and Lot'))
                this.condominium =  Object.assign(this.condominium,response.data.houses.filter(house => house.listing_type == 'Condominium'))
                this.lot =  Object.assign(this.lot,response.data.houses.filter(house => house.listing_type == 'Lot'))
                this.land  = Object.assign(this.land,response.data.houses.filter(house => house.listing_type == 'Land')) 
                this.houses = response.data.houses
            })
        },
        showHouse(id){
            console.log(id)
            this.$router.push({ name: 'Show House', params: { id} })
        },
        search(){
            this.$router.push({name: 'Search House'})
        }
    },
    filters: {

    },
}
</script>

<style>

</style>