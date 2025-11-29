<template>
<h1>Welcome</h1>
</template>

    
<script>
export default {
    name: 'Home',
     mounted () {
        let user = localStorage.getItem('use-info')
        if(!user) {
            this.$router.push({
                name: 'SignUp'})
        }
    }
}
</script>
