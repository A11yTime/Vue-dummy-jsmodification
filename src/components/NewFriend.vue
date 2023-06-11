<template> 
<form @submit.prevent="submitData">
 <div>
    <label for="form">Name</label>
    <input type="text" id="form" v-model="enteredName">
 </div>
 <div>
   <label for="form">Phone</label>
   <input type="tel" id="form" v-model="enteredPhone">
 </div>
 <div>
   <label for="form">E-mail</label>
   <input type="email" id="form" v-model="enteredEmail">
 </div>
 <div>
    <button>Add Contact</button>
 </div>
</form>
</template>

<script>
export default{
  name: 'NewFriend',
  components: {

  },
  emits: ['add-contact'],
  data(){
    return{
        enteredName: '',
        enteredPhone: '',
        enteredEmail: ''
    }
  },
  methods: {
    submitData(){
        this.$emit('add-contact',
        this.enteredName,
        this.enteredPhone,
        this.enteredEmail
        );
    }
  }
}
</script>

<style>
</style>