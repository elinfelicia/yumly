<script setup>
defineProps({
    modelValue: {
        type: String,
        default: ''
    },

});
const emit = defineEmits(['update:modelValue']);

</script>

<template> 
    <div class="searchbar">
        <input :value="modelValue" @input="emit('update:modelValue', $event.target.value)" type="text" placeholder="Search recipes..." />
    </div>
</template>

<style scoped>
.searchbar {
    width: 100%;
    max-width: 500px;
    margin: 0 auto;
}

.searchbar input {
    width: 100%;
    padding: 0.75rem 1rem;
    border: 2px solid #e0e0e0;
    border-radius: 0.5rem;
    font-size: 1rem;
    transition: border-color 0.3s, box-shadow 0.3s;
}

.searchbar input:focus {
    border-color: #647f81;
    outline: none;
    box-shadow: 0 0 0 3px rgba(100, 127, 129, 0.1);
}

.searchbar input::placeholder {
    color: #999;
}
</style>