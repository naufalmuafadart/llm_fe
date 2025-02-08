<template>
    <div class="login-container">
        <h2>Login</h2>
        <form @submit.prevent="handleLogin">
        <div class="form-group">
            <label for="email">Email:</label>
            <input
            type="email"
            id="email"
            v-model="email"
            placeholder="Enter your email"
            required
            />
        </div>
        <div class="form-group">
            <label for="password">Password:</label>
            <input
            type="password"
            id="password"
            v-model="password"
            placeholder="Enter your password"
            required
            />
        </div>
        <button type="submit">Login</button>
        </form>
        <p v-if="errorMessage" class="error-message">{{ errorMessage }}</p>
    </div>
</template>

<script>
import '~/assets/login/index.css'
export default {
  data() {
    return {
      email: '',
      password: '',
      errorMessage: '', // To display error messages
    };
  },
  methods: {
    handleLogin() {
      // Simple validation
      if (!this.email || !this.password) {
        this.errorMessage = 'Please fill in all fields.';
        return;
      }

      // Simulate login (replace with actual API call)
      if (this.email === 'user@example.com' && this.password === 'password') {
        alert('Login successful!');
        this.errorMessage = '';
        // Redirect to another page or perform other actions
      } else {
        this.errorMessage = 'Invalid email or password.';
      }
    },
  },
};
</script>

<style scoped>
@import url("~/assets/login/index.css");
.login-container {
    width: 50%;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 8px;
    background-color: #f9f9f9;
    text-align: center;
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%,-50%);
}

h2 {
    margin-bottom: 20px;
}

.form-group {
    margin-bottom: 15px;
    text-align: left;
}

label {
    display: block;
    margin-bottom: 5px;
    font-weight: bold;
}

input {
    width: 100%;
    padding: 8px;
    border: 1px solid #ccc;
    border-radius: 4px;
}

button {
    width: 100%;
    padding: 10px;
    background-color: #007bff;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

button:hover {
    background-color: #0056b3;
}

.error-message {
    color: red;
    margin-top: 10px;
}
</style>