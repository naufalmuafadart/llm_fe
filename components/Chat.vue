<template>
	<div class="chat-container">
		<Navbar />
		<ChatMessages :messages="messages" :is_disabled="isDisabled" />
		<div class="chat-input">
			<input
				v-model="newMessage"
				@keyup.enter="sendMessage"
				:disabled="isDisabled"
				placeholder="Ketik pesan..." />
			<button
				@click="sendMessage"
				:disabled="isDisabled">Kirim</button>
		</div>
	</div>
</template>

<script>
export default {
	data() {
		return {
			messages: [],
			newMessage: '',
			isDisabled: false,
		};
	},
	methods: {
		async sendMessage() {
			if (this.newMessage.trim() !== '') {
				const config = useRuntimeConfig();
				this.isDisabled = true;
				this.messages.push({ sender: 'Client', text: this.newMessage, content: []});

				const response = await fetch(config.public.BACK_END_URL, {
					method: 'POST',
					body: JSON.stringify({
						'message': this.newMessage
					}),
					headers: {
						'Content-Type': 'application/json'
					}
				});
				const responseJSON = await response.json();
				console.log({ responseJSON });
				this.newMessage = '';

				if (response.status == 200) {
					this.messages.push({ sender: 'Server', text: '', content: responseJSON['content'] });
				} else {
					this.messages.push({ sender: 'Server', text: '', content: [{ "element": "text", "text": "Tidak dapat membuat rute" }] });
				}
				this.isDisabled = false;
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