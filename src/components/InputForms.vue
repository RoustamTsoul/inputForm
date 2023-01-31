<template>
  
  <form class="formField" @submit.prevent="sendForm">
    <div class="title">
    <h1>{{ msg }}</h1>
    </div>

    <div class="field">
        <label class="label" for="firstName">First name : </label>
        <input  class="inputField" type="text" id="firstName" placeholder="Your first name..." required v-model="firstName">
    </div>
    
    <div class="field">
        <label class="label" for="secondName">Surname : </label>
        <input class="inputField" type="text" id="secondName" placeholder="Your surname..." required v-model="secondName">
    </div>
    
    <div class="field">
        <label class="label" for="tel">Phone number : </label>
        <input class="inputField" type="tel" id="tel" placeholder="Your phone number" required v-model="tel">
    </div>
    
    <div class="field">
        <label class="label" for="email">Email : </label>
        <input class="inputField" type="email" id="email" placeholder="Email" required v-model="email">
    </div>
    
    <div class="field">
        <label class="label" for="dateBirth">Date of birth : </label>
        <input class="inputField" type="date" id="dateBirth"  placeholder="Date of birth"  v-model="dateBirth">
    </div>
  

    <div class="field">
        <label class="label" for="dateStart">Time to start : </label>
        <input class="inputField" type="date" id="dateStart" placeholder="When you prefer to start"  v-model="dateStart">
    </div>
    
    <div class="field">
        <label class="label" for="password">Password : </label>
        <input class="inputField" type="password" id="password" placeholder="Password" required v-model="password">
        <div v-if="passwordError" class="error">{{ passwordError }}</div>
    </div>
    
    <div class="field">
        <label class="label" for="role">Role :</label>
        <select class="inputField" id="role" v-model="role" >
            <option value="developer">Web Developer</option>
            <option value="designer">Web Designer</option>
        </select>
    </div>
    

    <div class="field">
        <label class="label" for="rules"> Im agree with your rules </label>
        <input class="checkbox" type="checkbox" id="rules" required v-model="rules">
    </div>
    <button class="btn btn-agree">Send registration list</button>
  </form>
  
</template>

<script>
export default {
    name:'InputForms',
    props:{
        msg:String,
    },
data(){
    return{
        firstName:'',
        secondName:'',
        email:'',
        tel:'',
        dateBirth:'',
        dateStart:'',
        password:'',
        role:'',
        rules: false,
        passwordError:'',
        }
    },
    emits:['submit'],

    methods:{
    sendForm(){
    // password valid
    this.passwordError = this.password.length > 7 ? '' : 'Password must be at least 8 chars long'
       
      if(!this.passwordError){
            console.log('firstName: ',this.firstName)
            console.log('secondName: ',this.secondName)
            console.log('email: ',this.email)
            console.log('tel: ',this.tel)
            console.log('dateBirth: ',this.dateBirth)
            console.log('dateStart: ',this.dateStart)
            console.log('password: ',this.password)
            console.log('role: ',this.role)
            console.log('rules: ',this.rules)
            
            const formData ={
                firstName: this.firstName,
                secondName:this.secondName,
                email:this.email,
                tel:this.tel,
                dateBirth:this.dateBirth,
                dateStart:this.dateStart,
                password:this.password,
                role:this.role,
                rules:this.rules,
                passwordError:this.passwordError,
            }

            this.$emit('submit', formData)
            } 
        }
    }
}
</script>

<style scoped>
.formField{
    min-width: 400px;
    margin: 20px 40px;
    display: flex;
    flex-direction: column;
    background:white;
    color:black;
    text-align: left;
    padding: 25px;
    border-radius: 20px;
    background-image: linear-gradient(to left top, #86c19a, #a7b47f, #c1a578, #cd9783, #c98e97);
}

.title{
    color:#000000;
    font-size: 1rem;
    text-align: center;
    margin: 10px 10px;
}

.field{
    margin-top:2px;
    margin-bottom: 2px;
}

.label{
    color:black;
    display: inline-block;
    margin: 25px 0 15px;
    font-size:1rem;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: bold;
}

.inputField{
    display: block;
    padding: 10px 5px;
    width:90%;
    box-sizing: border-box;
    border: none;
    border-bottom: 2px solid rgb(10, 36, 71);
    color: rgba(0, 0, 0, 0.847);
    font-size: 1rem;
    font-weight: 200;
    background-image: linear-gradient(to left top, #98a79d, #c9d89b, #c1a578, #cd9783, #b6989c);
}

.checkbox{
    display: inline-block;
    width: 16px;
    margin:0px 0px 50px 0;
    position: relative;
    top: 2px;
}
.error{
    color: #fe0004;
    margin-top:10px;
    font-size: 0.8rem;
    font-weight: bold;
}

.btn{
    max-width: 400px;
    margin: 10px 10px;
    color:black;
    text-align: center;
    padding: 10px;
    border: none;
    border-radius: 10px;
    background-image: linear-gradient(to right, #f9d423 0%, #ff4e50 100%);
    font-size:1rem;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: bold;
}
.btn:hover{
    background-image: linear-gradient(to right, #8e7a15 0%, #d52326d4 100%);
}
</style>