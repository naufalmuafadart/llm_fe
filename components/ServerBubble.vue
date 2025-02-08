<template>
    <div class="message">
        <div class="text">
            {{ text }}
        </div>
    </div>
</template>

<script>
export default {
    props: ['text'],
}
</script>

<style scoped>
.message {
	margin-bottom: 10px;
	padding: 10px;
	border-radius: 4px;
}
</style>
