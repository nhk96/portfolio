<template>
    <div id="skill" class="skill">
        <div class="title">Skills</div>
        <div v-for="(skillCategory, index) in skillList" :key="index" class="skill-category">
            <div class="title">{{ skillCategory.skill }}</div>
            <div class="skill-list">
                <template v-for="items in skillCategory.skillsets" :key="items.name">
                    <div class="name-column">
                        {{ items.name }}
                    </div>
                    <div class="level-column">
                        <div class="progress-bar" :class="{
                            invalid: 'invalid' in items && items.invalid
                        }" :style="{ width: `${items.progress}%` }"></div>
                    </div>
                </template>
            </div>
            <div class="source" v-html="skillCategory.source"></div>
        </div>

    </div>
</template>

<script setup lang="ts">

interface Skillset {
    name: string;
    progress: number;
    invalid?: boolean;
}


interface SkillCategory {
    skill: string;
    skillsets: Skillset[];
    source: string;
}

const skillList: SkillCategory[] = [
    {
        skill: 'Technical Skill(s)',
        skillsets: [
            { name: 'HTML', progress: 50, invalid: true },
            { name: 'CSS', progress: 50, invalid: true },
            { name: 'JavaScript (Vanilla)', progress: 50, invalid: true },
            { name: 'VueJs', progress: 50, invalid: true },
            { name: 'ReactJs', progress: 50, invalid: true },
            { name: 'Git', progress: 50, invalid: true },
            { name: 'CI/CD', progress: 50, invalid: true },

        ],
        source: "I can't really give myself a score since I'm still learning and improving."
    },
    {
        skill: 'Soft Skill(s)',
        skillsets: [
            { name: 'Teamwork', progress: 80 },
            { name: 'Problem solving', progress: 80 },
            { name: 'Time Management', progress: 100 },
            { name: 'Organizational skills', progress: 80 },
            { name: 'Productivity', progress: 80 },
            { name: 'Adaptability', progress: 80 },
        ],
        source: 'Scores are based on <a href="https://drive.google.com/file/d/1cotnSdRKS0zIOy3IA7ncsP1qNCAbqy57/view?usp=sharing" target="_blank">performance evaluation of year 2024</a>.'
    },
];
</script>

<style scoped>
.skill {
    width: 50%;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    gap: 2rem;
    padding: 2rem 0;

    .title {
        font-size: 2rem;
        font-weight: 900;
        font-family: var(--primary-font);
    }

    .subtitle {
        font-size: 1.5rem;
        font-weight: 700;
        font-family: var(--secondary-font);
    }

    .skill-category {
        display: flex;
        flex-direction: column;
        gap: 0.5rem;

        .title {
            font-size: 1.5rem;
            font-weight: 700;
            font-family: var(--secondary-font);
        }

        .skill-list {
            display: grid;
            grid-template-columns: 30% 1fr;
            width: 100%;
            gap: 0.25rem 0.5rem;
        }
    }

    .source {
        font-size: 0.75rem;
        opacity: 0.5;
    }

    .name-column {
        font-size: 0.75rem;
    }

    .level-column {
        align-items: center;
        background: #848484;
        border-radius: 0.25rem;

        .progress-bar {
            height: 100%;
            border-radius: 0.25rem;
            background: #212121;

            &.invalid {
                background: red;
            }
        }
    }
}

@media (max-width: 768px) {
    .skill {
        width: 100%;
        padding: 1rem;
    }

    .skill-list {
        grid-template-columns: 1fr;
    }
}
</style>
