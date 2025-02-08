<template>
    <ClientBubble
        v-if="sender === 'Client'"
        :text="text" />
    <ServerBubble
        v-if="sender === 'Server'"
        :text="text" />
</template>

<script>
export default {
    props: ['sender', 'text'],
    setup(props) {
        console.log(props.sender)
    }
}
</script>
