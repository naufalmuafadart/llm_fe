<template>
    <ClientBubble
        v-if="sender === 'Client'"
        :text="text" />
    <ServerBubble
        v-if="sender === 'Server'"
        :content="content"
        :text="text" />
</template>

<script>
export default {
    props: ['sender', 'text', 'content'],
    setup(props) {
        console.log(props.sender)
    }
}
</script>
