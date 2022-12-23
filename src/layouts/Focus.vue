<template>
    <div :style="`border: 2px solid ${props.color}; padding: 18px`">
    <pre>[using focus layout]</pre>
        <slot />
        
    </div>
</template>



<script setup>

    const props = defineProps({
        color: {
            default: 'black'
        }
    })
</script>