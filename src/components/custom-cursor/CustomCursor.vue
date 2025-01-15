<template>
    <div class="cursor" ref="cursor">
        <div class="dot"></div>
    </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const cursor = ref(null);

const moveCursor = (e) => {
    cursor.value.style.left = `${e.pageX}px`;
    cursor.value.style.top = `${e.pageY}px`;
};

const clickCursor = () => {
    cursor.value.classList.add('click');
    setTimeout(() => cursor.value.classList.remove('click'), 200);
};

const toggleHoverClass = (e) => {
    cursor.value.classList.toggle('hover', e.type === 'mouseenter');
};

const toggleHoldClass = (e) => {
    cursor.value.classList.toggle('hold', e.type === 'mousedown');
};

onMounted(() => {
    document.addEventListener('mousemove', moveCursor);
    document.addEventListener('click', clickCursor);
    document.addEventListener('mousedown', toggleHoldClass);
    window.addEventListener('mouseup', toggleHoldClass);
    document.querySelectorAll('a, button').forEach(element => {
        element.addEventListener('mouseenter', toggleHoverClass);
        element.addEventListener('mouseleave', toggleHoverClass);
    });
});

onUnmounted(() => {
    document.removeEventListener('mousemove', moveCursor);
    document.removeEventListener('click', clickCursor);
    document.removeEventListener('mousedown', toggleHoldClass);
    window.removeEventListener('mouseup', toggleHoldClass);
    document.querySelectorAll('a, button').forEach(element => {
        element.removeEventListener('mouseenter', toggleHoverClass);
        element.removeEventListener('mouseleave', toggleHoverClass);
    });
});
</script>

<style scoped>
@media screen and (max-width: 768px) {
    .cursor {
        display: none;
    }

}


.cursor {
    position: fixed;
    width: 1.125rem;
    /* 1.5rem * 0.75 */
    height: 1.125rem;
    /* 1.5rem * 0.75 */
    border-radius: 50%;
    border: solid 1px red;
    background: rgba(255, 0, 0, 0.25);
    pointer-events: none;
    z-index: 999;
    transition: transform 0.1s, border-width 0.1s, width 0.1s, height 0.1s;
    transform: translate(-50%, -50%);
}

.cursor.click {
    animation: clickAnimation 0.2s forwards;
}

.cursor.hold {
    width: 0.75rem;
    /* 1rem * 0.75 */
    height: 0.75rem;
    /* 1rem * 0.75 */
}

.cursor.hover .dot {
    width: 0.5625rem;
    /* 0.75rem * 0.75 */
    height: 0.5625rem;
    /* 0.75rem * 0.75 */
}

@keyframes clickAnimation {

    0%,
    100% {
        width: 1.125rem;
        /* 1.5rem * 0.75 */
        height: 1.125rem;
        /* 1.5rem * 0.75 */
    }

    50% {
        width: 0.75rem;
        /* 1rem * 0.75 */
        height: 0.75rem;
        /* 1rem * 0.75 */
    }
}

.dot {
    width: 0.375rem;
    /* 0.5rem * 0.75 */
    height: 0.375rem;
    /* 0.5rem * 0.75 */
    background-color: red;
    border-radius: 50%;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}
</style>
