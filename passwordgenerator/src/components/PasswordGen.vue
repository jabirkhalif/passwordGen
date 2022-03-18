<template>

<div class="bg-gray-200 h-screen w-screen flex  justify-center items-center">

<div class="bg-green-900 shadow-lg border-l-rose-400 border  rounded-md h-[230px] w-[400px] flex-row items-center justify-center p-4 ">
 <p class="text-white font-bold  tracking-tight mb-3">Welcome to random password generator. click the button below to get a random Password</p>
 <p class="bg-yellow-900 text-white  font-mono p-3 border rounded-lg">
     your password is <span class="bg-blue-500 font-bold px-2 py-1 rounded-md" v-if="password">{{password}}</span> 
</p>
<div class="flex justify-around">
<button class="bg-green-600  mt-3 text-white  font-bold text-sm p-3 rounded-md shadow" @click="generatePassword">
    Generate Password
</button>
<button class="bg-green-400  mt-3 text-white  font-bold text-sm p-3 rounded-md shadow"  @click="reset">
    Reset
</button>
</div>


</div>


</div>


</template>

<script>
export default  {
    data(){
        return {
        password: '',
        
        }
        
    }, 
    methods:{
        generatePassword() {
            var characters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789$#*&^!';
            for (let i = 0; i <=8; i++) {
            var  randomPass = Math.floor(Math.random() * 
            characters.length);
            this.password += characters.substring(randomPass, randomPass +1)
            }
            console.log(this.password.length)
            if (this.password.length >9 ) {
                 this.password = ''
                alert('please, reset the current password before generating a new one.')
            }
        
        },
       reset(){
           this.password = ''
       }
    }

}


</script>