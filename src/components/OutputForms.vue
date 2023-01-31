<template>
 
  <form class="completeField" @submit.prevent="resetForm">
     <div class="title">
        <h1>{{ msg }}</h1>
    </div> 
    <div class="fields">
        <div class="textField">First name :{{firstName}}</div>
    </div>
    <div class="fields">
        <div class="textField">Surname :{{secondName}}</div>
    </div>
        
    <div class="fields">
        <div class="textField">Phone number :{{tel}}</div>
    </div>
        
    <div class="fields">
        <div class="textField">Email :{{email}}</div>
    </div>
        
    <div class="fields">
        <div class="textField">Date of birth :{{dateBirth}}</div>
    </div>
        
    <div class="fields">
        <div class="textField">Time to start :{{dateStart}}</div>
    </div>
        
    <div class="fields">
        <div class="textField">Password :{{password}}</div>
    </div>
       
    <div class="fields">
        <div class="textField">Position :{{role}}</div>
    </div>
        
    <div class="fields">
        <div class="textField">Term :{{rules}}</div>
    </div>
    
  </form>

  
</template>

<script>

export default {
    name:'OutputForms',
    props:{
        msg:String,
        //задекларировать пропсы и связать с шаблоном
        firstName:String,
        secondName:String,
        email:String,
        tel:String,
        dateBirth:String,
        dateStart:String,
        password:String,
        role:String,
        rules:String ,
        passwordError:String,
    },
}
</script>

<style scoped>
.completeField{
    min-width: 400px;
    margin: 20px 40px;
    display: flex;
    flex-direction: column;
    background:white;
    color:black;
    text-align: left;
    padding: 25px;
    border-radius: 10px;
    background-image: linear-gradient(to bottom, #a386c1, #cb93b4, #dca9ae, #e0c2b8, #e2dad1);
}

.title{
    color:#0a4a47;
    font-size: 1rem;
    text-align: center;
    margin: 10px 10px;
}

.fields{
    display: inline-block;
    color:black;
    margin: 25px 0 15px;
    font-size:1rem;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: bold;
    box-sizing: border-box;
    border: none;
    border-bottom: 2px solid rgb(201, 28, 66);
    
}
</style>