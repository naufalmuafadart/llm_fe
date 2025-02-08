<template>
    <div class="message-container">
        <div class="message">
            <div class="text">
                {{ text }}
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['text'],
}
</script>

<style scoped>
.message-container {
    display: flex;
    flex-direction: row;
    justify-content: end;
}

.message {
	margin-bottom: 10px;
	padding: 10px;
	background-color: #e9ecef;
	border-radius: 4px;
    width: max-content;
}

.text {
    text-align: right;
}
</style>
