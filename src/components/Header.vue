<script setup>

</script>

<template>
    <header>
        <img src="@/assets/logo.svg" alt="Yumly Logo" class="logo" />
        <h1>Yumly</h1>
    </header>
</template>

<style scoped>
header {
    background-color: #647f81;
    color: #fff;
    padding: 1rem 2rem;
    display: flex;
    align-items: center;
    gap: 1rem;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.logo {
    height: 40px;
    width: auto;
    display: block;
    object-fit: contain;
}

header h1 {
    margin: 0;
    font-size: 1.5rem;
}
</style>
