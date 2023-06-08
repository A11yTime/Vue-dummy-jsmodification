<template>
<li>
    <h2>{{ name }} {{ friendIsFavorite ? '(Favorite)' : '' }}</h2>
    <button @click="toggleFavorite">Toggle Favorite</button>
    <button @click="toggleDetails" :aria-expanded="detailsAreVisible">{{detailsAreVisible ? 'Hide' : 'Show'}} Details</button>
    
    <ul v-if="detailsAreVisible">
        <li><strong>Phone:</strong>{{ phoneNumber }}</li>
        <li><strong>Email:</strong>{{ emailAddress }}</li>
    </ul>
</li>
</template>
 <script>
 export default {
    // props: ['name','phoneNumber','emailAddress','isFavorite'],
    props:{
        name: {
            type: String,
            requrired: true,
        },
        phoneNumber: {
            type: String,
            requrired: true,
        },
        emailAddress: {
            type: String,
            requrired: true,
        },
        isFavorite: {
            type: Boolean,
            requrired: false,
            default: false,
            // validaton: function(value){
            //     return value === '1' || value === '0'
            // }
        }
        
    },
     data(){
        return{
            detailsAreVisible: false,
            friendIsFavorite: this.isFavorite
       };
     },
     methods: {
        toggleDetails(){
            this.detailsAreVisible = !this.detailsAreVisible
        },
        toggleFavorite(){
         this.friendIsFavorite= !this.friendIsFavorite
        }
     }
 }
</script>