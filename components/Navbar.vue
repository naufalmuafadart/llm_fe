<template>
    <header class="header">
        <!-- Logo on the left -->
        <div class="logo">
        <img
            src="https://eswpcd25uod.exactdn.com/blog/wp-content/uploads/2017/05/01-1024x1024.jpg?strip=all&lossy=1&ssl=1"
            width="50"
            height="50"
            alt="Logo" />
        </div>

        <!-- Account icon and dropdown on the right -->
        <div class="account" @click="toggleDropdown">
        <img
            src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR2qfZHidb__TM3Du79UTEPyCqTD3ybvBrhIQ&s"
            width="50"
            height="50"
            alt="Account" class="account-icon" />
        <!-- Dropdown menu -->
        <div v-if="isDropdownVisible" class="dropdown">
            <ul>
                <li @click="logout">Logout</li>
            </ul>
        </div>
        </div>
    </header>
</template>

<script>
export default {
    data() {
        return {
            isDropdownVisible: false, // Controls dropdown visibility
        };
    },
    methods: {
    // Toggle dropdown visibility
    toggleDropdown() {
        this.isDropdownVisible = !this.isDropdownVisible;
    },
    // Navigate to profile
    navigateToProfile() {
        alert('Navigating to profile...');
        this.isDropdownVisible = false; // Close dropdown
    },
    // Logout
    logout() {
        alert('Logging out...');
        this.isDropdownVisible = false; // Close dropdown
    },
    },
};
</script>

<style scoped>
.header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px 20px;
    background-color: #f8f9fa;
    border-bottom: 1px solid #ddd;
}

.logo img {
    height: 50px;
}

.account {
    position: relative;
    cursor: pointer;
}

.account-icon {
    height: 30px;
    width: 30px;
    border-radius: 50%;
}

.dropdown {
    position: absolute;
    top: 40px;
    right: 0;
    background-color: white;
    border: 1px solid #ddd;
    border-radius: 4px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    z-index: 1000;
}

.dropdown ul {
    list-style: none;
    margin: 0;
    padding: 0;
}

.dropdown ul li {
    padding: 10px 20px;
    cursor: pointer;
}

.dropdown ul li:hover {
    background-color: #f1f1f1;
}
</style>
