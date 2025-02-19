<template>
    <div class="menu">
        <div class="introduction">
            <div class="title">nghokit</div>
            <div class="subtitle">Fulltime Frontend Developer (VueJs & ReactJs) and Part-time Web (UI/UX) Designer</div>
            <div class="description">Over 5 years of experience in web development, specializing in UI/UX design and
                front-end development. Proficient in creating and designing web applications with ReactJs and VueJs,
                along with their libraries. Skilled in integrating Artificial Intelligence (AI) to enhance development
                efficiency.</div>
        </div>
        <div class="quick-links">
            <a v-for="link in quickLinks" :key="link.id" :href="link.href" @click.prevent="scrollToSection(link.id)">
                {{ link.text }}
            </a>
        </div>
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const quickLinks = ref([
    { id: 'experiences', href: '#experiences', text: 'Experiences' },
    { id: 'education', href: '#education', text: 'Educations' },
    { id: 'skill', href: '#skill', text: 'Skills & Tools' },
    { id: 'project', href: '#project', text: 'Projects' }
]);

function scrollToSection(id: string) {
    const element = document.getElementById(id);
    if (element) {
        element.scrollIntoView({ behavior: 'smooth' });
    }
}
</script>

<style scoped>
.menu {
    background: light-dark(#fff, #212121);
    filter: drop-shadow(0 0 0.75rem rgba(0, 0, 0, 0.1));
    display: flex;
    flex-direction: column;
    gap: 2rem;
    justify-content: center;
    align-items: center;
    padding: 2rem;

    .introduction {
        display: flex;
        flex-direction: column;

        .title {
            font-family: var(--primary-font);
            font-weight: bolder;
            font-size: 3rem;
        }

        .subtitle {
            font-family: var(--secondary-font);
        }

        .description {
            margin-top: 1rem;
            font-family: var(--tertiary-font);
            font-size: 0.75rem;
            opacity: 0.75;
        }
    }

    .quick-links {
        display: flex;
        flex-wrap: wrap;
        gap: 0.25rem;
        justify-content: flex-start;

        a {
            font-family: var(--secondary-font);
            font-size: 1rem;
            color: light-dark(#000, #fff);
            text-decoration: none;
            padding: 0.5rem 1rem;
            border-radius: 0.5rem;
            background: light-dark(rgba(0, 0, 0, 0.1), rgba(255, 255, 255, 0.1));
            transition: all 0.5s;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;

            &:hover {
                background: rgba(0, 0, 0, 0.25);
            }
        }
    }
}

@media (max-width: 768px) {
    .menu {
        padding: 1rem;
        gap: 1rem;
    }
}
</style>