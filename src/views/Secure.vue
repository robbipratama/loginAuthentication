<template>
    <div id="secure">
        <h1 class="loginarea">LOGIN AREA</h1>
        <p class="caption">
            You're Logged In
        </p>
    </div>
</template>

<script>
    export default {
        name: 'Secure',
    }
</script>

<style scoped>
    #secure {
        background-color: transparent;
        padding: 20px;
        margin-top: 10px;
        border-radius: 50px;
        box-shadow: 10px 15px 30px 0 teal;
    }

    .loginarea {
        color: teal;
        font-family: monospace;
        font-size: 50px;
    }

    .caption {
        color: teal;
        font-family: monospace;
        font-size: 25px;
    }
</style>