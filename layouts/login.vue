<template>
    <div class="chat-layout">
        <Nuxt />
    </div>
</template>
  
<script>
    export default {
        name: 'LoginLayout',
    };
</script>
  
<style>
    html, body {
        margin: 0;
        padding: 0;
        height: 100%;
        font-family: Arial, sans-serif;
    }

    .chat-layout {
        display: flex;
        flex-direction: column;
        height: 100vh;
        justify-content: center;
    }
</style>
