<template>
    <div class="chat-messages" ref="chatMessage">
        <Bubble
            v-for="(message, index) in messages"
            :sender="message.sender"
            :content="message.content"
            :text="message.text" />
        <Loader v-if="is_disabled" />
    </div>
</template>

<script>
export default {
    props: {
        messages: {
            required: true,
        },
        is_disabled: {
            required: true,
        }
    },
    updated() {
        this.scrollToBottom()
    },
    methods: {
        scrollToBottom() {
            const div = this.$refs.chatMessage;
            div.scrollTop = div.scrollHeight; // Scroll to the bottom
        },
    },
};
</script>
