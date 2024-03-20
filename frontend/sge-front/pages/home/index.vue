<script setup lang="ts">
const{ signOut } = useAuth();
    definePageMeta({
        middleware: 'auth'
    })

    const submitLogout = ()=>{
        signOut({redirect: false}).then(()=>{
            console.log("Successfully performed the logout");
            navigateTo("/")
        }).catch((error)=>{
            console.log("error when trying logout ", error);
        })

    }
</script>

<template>
    <div>
        <h1>minha tela home</h1>
        <button @click="submitLogout" class="customButton">FAZER LOGOUT</button>
    </div>
</template>

<style lang="scss">
</style>