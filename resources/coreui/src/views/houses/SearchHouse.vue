<template>
   <div>
        <div>
            <Navbar/>
        <section class="container">
            <div class="search">
                <div class="search-address">
                        <div class="search-item">
                            <label>Country</label>
                            <input type="text" placeholder="Country" v-model="search.country"/>
                        </div>

                        <div class="search-item">
                            <label>Province</label>
                            <input type="text" placeholder="Province" v-model="search.province"/>
                        </div>

                        <div class="search-item">
                            <label>City</label>
                            <input type="text" placeholder="City" v-model="search.city"/>
                        </div>

                        <div class="search-item">
                            <label>Listing Type</label>
                            <select v-model="search.listing_type">
                                <option value="House and Lot">HOUSE AND LOT</option>
                                <option value="Condominium">CONDIMINIUM</option>
                                <option value="Land">LAND</option>
                                <option value="Lot">LOT</option>
                            </select>
                        </div>
                </div>

                <div class="search-price">
                    <div class="search-item">
                        <label>Price Range</label>
                        <div class="price-range">
                            <div style="margin-right: 3%;">
                                <input type="number" placeholder="Minimum" v-model="search.minPrice"/>
                            </div>
                            <div>
                                <p>to</p>
                            </div>
                            <div  style="margin-left: 3%;">
                                <input type="number" placeholder="Maximum" v-model="search.maxPrice"/>
                            </div>
                        </div>
                    </div>
        
                </div>
                <div class="search-item">
                    <button class="search-btn" @click="searchHouse">SEARCH</button>
                </div>
            </div>
        </section>

        <div class="container">
            <section class="content">
            <h1 class="content-title">LISTING</h1>

            <div class="house-lot-content" >
                <div class="house-item" v-for="(house,index) in searchHouses" :key="index" @click="showHouse(house.id)">
                    <div class="body">
                        <template v-if="house.images.length">
                            <img :src="'/../storage/' + house.images[0].path" class="image card-img-top"/>
                        </template>
                        <template v-else>
                        NO IMAGE AVAILABLE
                        </template>
                        <h1>₱ {{new Intl.NumberFormat().format(house.price)}}</h1>
                    </div>
                    <div class="footer">
                        <div class="footer-details">
                            <label>BEDS {{house.beds}}</label>
                            <label>BATHROOM {{house.bathroom}}</label>
                            <label>LOT AREA {{house.lot_area}} sqft</label>
                        </div>
                        <div class="footer-address">
                            <p>{{house.street + ' ' + house.city + ' ' + house.province + ' ' + house.country}}</p>
                            <p>{{house.listing_type}}</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <Footer/>
       </div>
   </div>
</template>

<script>

import Navbar from '../../custom/Navbar.vue'
import Footer from '../../custom/Footer'
export default {
    components : {Navbar,Footer},
    data(){
        return{
            houses : [],
            searchHouses : [],
            search : {
                country : '',
                province : '',
                city : '',
                minPrice : 100000,
                maxPrice : 10000000,
                listing_type : 'House and Lot'
            }
        }
    },

    created(){
        this.getHouses()
    },
    methods: {
       getHouses(){
            this.axios.get('house/index')
            .then(response => {
               this.houses = response.data.houses
               this.searchHouses = response.data.houses
            })
        },
        showHouse(id){
            this.$router.push({ name: 'Show House', params: { id} })
        },
        searchHouse(){

            console.log(this.houses)
            // this.houses.forEach(house => {
            //     console.log(Math.floor(house.price) + '<' + Math.floor(this.search.minPrice))
            //     console.log(Math.floor(house.price) < Math.floor(this.search.minPrice))
            // })
            this.searchHouses = this.houses.filter(house => house.listing_type == this.search.listing_type)
            if(this.search.minPrice != 0 && this.search.maxPrice != 0){

                 this.searchHouses = this.searchHouses.filter(house => Math.floor(house.price) > Math.floor(this.search.minPrice))
                 this.searchHouses = this.searchHouses.filter(house => Math.floor(house.price) < Math.floor(this.search.maxPrice))
            }
            if(this.search.country != ''){
                 this.searchHouses = this.searchHouses.filter(house => house.country == this.search.country)
            }

            if(this.search.province != ''){
                 this.searchHouses = this.searchHouses.filter(house => house.province == this.search.province)
            }

             if(this.search.city != ''){
                 this.searchHouses = this.searchHouses.filter(house => house.city == this.search.city)
            }
            console.log(this.searchHouses)
        }
    },
    filters: {

    },
}
</script>
