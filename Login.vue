<template>
<img class="logo" src="../assets/image.png" />
<h1>Login</h1>
<div class="login">
    <input type="Email" v-model="email" placeholder="Enter Email" />
    <input type="Password" v-model="password" placeholder="Enter password" />
    <button>Login</button>
    <p>
        <router-link to="/sign-up">Sign-Up</router-link>
    </p>

</div>
</template>

    
<script>
export default {
    name: 'Login'
}
</script>
