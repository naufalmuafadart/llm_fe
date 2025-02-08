<template>
	<div class="chat-container">
		<Navbar />
		<ChatMessages :messages="messages" />
		<div class="chat-input">
			<input
				v-model="newMessage"
				@keyup.enter="sendMessage"
				placeholder="Ketik pesan..." />
			<button
				@click="sendMessage">Kirim</button>
		</div>
	</div>
</template>

<script>
export default {
	data() {
		return {
			messages: [
				// { sender: 'Server', text: 'Hello!' },
				// { sender: 'Client', text: 'Hi there!' },
			],
			newMessage: '',
		};
	},
	methods: {
		sendMessage() {
			if (this.newMessage.trim() !== '') {
				this.messages.push({ sender: 'Client', text: this.newMessage });
				this.messages.push({ sender: 'Server', text: 'Jawaban' });
				this.newMessage = '';
			}
		},
	},
};
</script>

<style scoped>
.chat-container {
	display: flex;
	flex-direction: column;
	height: 100vh;
	background-color: #f9f9f9;
}

.chat-messages {
	flex: 1;
	padding: 15px;
	overflow-y: auto;
	background-color: white;
}

.chat-input {
	display: flex;
	padding: 10px;
	background-color: #f1f1f1;
	border-top: 1px solid #ccc;
}

.chat-input input {
	flex: 1;
	padding: 10px;
	border: 1px solid #ccc;
	border-radius: 4px;
	margin-right: 10px;
}

.chat-input button {
	padding: 10px 15px;
	background-color: #007bff;
	color: white;
	border: none;
	border-radius: 4px;
	cursor: pointer;
}

.chat-input button:hover {
	background-color: #0056b3;
}
</style>