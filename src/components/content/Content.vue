<template>
    <div class="content">

        <Experiences />
        <Education />
        <Skills />
    </div>
</template>

<script setup lang="ts">
import Experiences from '@/views/Experiences/Experiences.vue';
import Education from '@/views/Education/Education.vue';
import Skills from '@/views/Skills/Skills.vue';

</script>

<style scoped>
.content {
    background: #fff;
    color: #000;
    height: 100%;
    overflow: auto;
    display: flex;
    flex-direction: column;
    padding-top: 2rem;
    padding-bottom: 10rem;

}

@media (max-width: 768px) {
    .content {
        flex-direction: column;
        gap: 2rem;
    }
}
</style>