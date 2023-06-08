<template>
<li>
    <h2>{{ name }}</h2>
    <button @click="toggleDetails" :aria-expanded="detailsAreVisible">{{detailsAreVisible ? 'Hide' : 'Show'}} Details</button>
    <ul v-if="detailsAreVisible">
        <li><strong>Phone:</strong>{{ phoneNumber }}</li>
        <li><strong>Email:</strong>{{ emailAddress }}</li>
    </ul>
</li>
</template>
 <script>
 export default {
    props: [
        'name',
        'phoneNumber',
        'emailAddress'
    ],
     data(){
        return{
            detailsAreVisible: false,
            friend: {
                id: 'Rubab',
                name: 'Rubab Rana',
                phone: '245 823 5874',
                email: 'rubab@localhost.com'
            }
        }
     },
     methods: {
        toggleDetails(){
            this.detailsAreVisible = !this.detailsAreVisible
        }
     }
 }
</script>