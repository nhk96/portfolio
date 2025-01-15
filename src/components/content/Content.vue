<template>
    <div class="content">

        <Experiences />
        <Education />
        <Skills />
        <Project />
    </div>
</template>

<script setup lang="ts">
import Experiences from '@/views/experiences/Experiences.vue';
import Education from '@/views/education/Education.vue';
import Skills from '@/views/skills/Skills.vue';
import Project from '@/views/projects/Project.vue';

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