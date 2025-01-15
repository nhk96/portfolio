<template>
    <div class="popover-container">
        <button @click="showPopover" :popovertarget="'popover-' + id">
            <slot name="trigger"></slot>
        </button>
        <div v-if="isPopoverVisible" :id="'popover-' + id" class="popover">
            <slot name="content"></slot>
        </div>
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

defineProps({
    id: String,
});

const isPopoverVisible = ref(false);

const showPopover = () => {
    isPopoverVisible.value = true;
    setTimeout(() => {
        isPopoverVisible.value = false;
    }, 2000);
};
</script>

<style scoped>
.popover-container {
    display: flex;
    align-items: center;
}

button {
    background: none;
    border: none;
    width: max-content;
    padding: 0;
    margin: 0;
    color: inherit;
}

.popover {
    position: absolute;
    top: 50%;
    left: 50%;
    font-size: 1rem;
    transform: translate(-50%, -50%);
    z-index: 1;
    background: light-dark(#fff, #212121);
    color: light-dark(#000, #fff);
    border-radius: 8px;
    padding: 10px;
    border: 1px solid transparent;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}
</style>