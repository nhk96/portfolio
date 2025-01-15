<template>
    <div class="landing">
        <Menu />
        <Content />
    </div>
</template>

<script setup lang="ts">
import Menu from '@/components/menu/Menu.vue'
import Content from '@/components/content/Content.vue'

</script>

<style scoped>
.landing {
    display: grid;
    grid-template-columns: 1fr 4fr;
    height: 100vh;
    transition: all 0.5s;
    overflow-y: scroll;

}

@media (max-width: 768px) {
    .landing {
        grid-template-columns: 1fr;
    }
}
</style>