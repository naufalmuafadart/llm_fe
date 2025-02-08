<template>
    <div>
      <Chat />
    </div>
</template>
  
<script>
import Chat from '~/components/Chat.vue';
import '~/assets/chat/index.css'

export default {
    layout: 'chat',
    components: {
        Chat,
    },
};
</script>

<style>
@import url("~/assets/chat/index.css");
</style>
