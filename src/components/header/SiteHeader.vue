<template>
    <header class="header">
        <div class="header-content">
            <h1 class="logo">Lucas & Ester</h1>
            <nav class="nav-links">
                <!-- Add navigation links here if needed -->
            </nav>
        </div>
    </header>
</template>

<script setup>
// Header logic here
</script>

<style scoped>
.header {
    position: fixed;
    top: 1.5rem;
    left: 50%;
    transform: translateX(-50%);
    width: 90%;
    max-width: 1200px;
    height: auto;
    background: rgba(255, 255, 255, 0.1);
    backdrop-filter: blur(10px);
    -webkit-backdrop-filter: blur(10px);
    border: 1px solid rgba(255, 255, 255, 0.2);
    border-radius: 50px;
    padding: 0.75rem 2rem;
    z-index: 100;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
    transition: all 0.3s ease;
}

.header-content {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.logo {
    font-family: 'Playfair Display', serif;
    font-size: clamp(1.2rem, 3vw, 1.8rem);
    color: white;
    font-weight: 500;
    margin: 0;
    text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.3);
}

@media (max-width: 600px) {
    .header {
        top: 1rem;
        padding: 0.5rem 1.5rem;
        border-radius: 30px;
    }
}
</style>
