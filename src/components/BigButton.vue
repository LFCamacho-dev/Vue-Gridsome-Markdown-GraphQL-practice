<template>

    <div>
        <button class="btn" :style="`background-color: ${props.color};`">Big Button</button>    
    </div>

</template>


<script setup>
    const props = defineProps({
        color: {
            type: String,
            default: "gray"
        }
    })
    
</script>


<style>

.btn {
    padding: 22px;
}

</style>
