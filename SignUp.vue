<template>
<img class="logo" src="../assets/image.png" />
<h1>Sign Up</h1>
<div class="register">
    <input type="text" v-model="name" placeholder="Enter Name" />
    <input type="Email" v-model="email" placeholder="Enter Email" />
    <input type="Password" v-model="password" placeholder="Enter password" />
    <button v-on:click="signUp">Sign Up</button>
    <p><router-link to="/login">Login</router-link></p>

</div>
</template>

<script>
import axios from 'axios'
export default {
    name: 'SignUp',
    data() {
        return {
            name: "",
            email: "",
            password: "",
        }
    },
    methods: {
        async signUp() {
            console.log("signUp", this.name, this.email, this.password)
            let result = await axios.post("http://localhost:3000/use", {
                email: this.email,
                name: this.name,
                password: this.password,
            });
            console.log(result);
            if (result.status == 201) {}
            localStorage.setItem("use-info", JSON.stringify(result.data))
            this.$router.push({
                name: 'Home'
            })
        }
    },
    mounted () {
        let user = localStorage.getItem('use-info')
        if(user) {
            this.$router.push({
                name: 'Home'})
        }
    }
}
</script>

<style>

</style>
