<template src="../../templates/house/houselist.html">
    
</template>

<script>
export default {
    data(){
        return{
            houses : []
        }
    },
    methods : {
        getHouses(){
            this.axios.get('house/index')
            .then(response => {
               this.houses = response.data.houses
            })
        },
        newHouse(){
            this.$router.push('/houses/create')
        },
        deleteHouse(id){
            let isDeleted = 0
            this.$swal.fire({
                    title: "Are you sure?",
                    text: "You will not be able to recover this data",
                    icon: "warning",
                    showCancelButton: true,
                    confirmButtonColor: '#DD6B55',
                    confirmButtonText: 'Yes, I am sure!',
                    cancelButtonText: "No, cancel it!",
                    closeOnConfirm: false,
                    closeOnCancel: false,
                    dangerMode: true,
                    }).then(function(isConfirm) {
                    if (isConfirm) {
    
                            // axios.delete(`house/delete/${id}`).then(response => {
                            // let index = this.houses.findIndex(house => house.id == id);
                            // this.houses.splice(index,1);
                            isDeleted = 1
                            console.log(isDeleted)
                            // this.$swal('System','Sucessfully deleted','success')
                        // })
                    }
            }).then(() => {
                if(isDeleted){
                    axios.delete(`house/delete/${id}`).then(response => {
                        let index = this.houses.findIndex(house => house.id == id);
                        this.houses.splice(index,1);
                        this.$swal('System','Sucessfully deleted','success')
                    })
                }
            })
        }
    },
    created(){
        this.getHouses()
        console.log(this.houses)
    }
}
</script>

<style>
        .house-list{
            height: 100vh;
            display: flex;
            margin: 0 auto;
            justify-content: center;
        }
        th{
            margin-left: 10%;
        }
        tr td{
            margin: 3%;
        }
</style>