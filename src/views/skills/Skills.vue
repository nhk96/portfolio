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
        <div class="skill-category">
            <div class="title">Tool(s)</div>
            <div class="toolsets">
                <div class="tool" v-for="items in toolsets">
                    <img :src="items.logo" :alt="items.name" />
                </div>

            </div>
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

const toolsets = [
    {
        name: "Notion",
        logo: "https://logos-world.net/wp-content/uploads/2024/08/notion-symbol.png"
    },
    {
        name: 'GitLab',
        logo: 'https://1000logos.net/wp-content/uploads/2022/03/Gitlab-Logo.png'
    },
    {
        name: "Jira",
        logo: "https://img2.storyblok.com/filters:format(webp)/f/84825/499x244/9266fa6ddf/__jira-unnamed.png"
    },
    {
        name: 'VSCode',
        logo: 'https://media.licdn.com/dms/image/v2/D4D12AQHV7to6hMRPUg/article-cover_image-shrink_720_1280/article-cover_image-shrink_720_1280/0/1715455222364?e=2147483647&v=beta&t=fMajdXUMNcvoBZ6DCF3hN4tZJATei2dSJyTJ6zVfJGQ'
    },

    {
        name: 'GitHub Copilot',
        logo: 'https://assets.bitdegree.org/images/github-copilot-review-logo-square.png?tr=w-250'
    },
    {
        name: 'Photoshop',
        logo: 'https://logos-world.net/wp-content/uploads/2020/11/Adobe-Photoshop-Logo-2015-2019.png'
    },
    {
        name: 'Figma',
        logo: 'https://cdn4.iconfinder.com/data/icons/logos-brands-in-colors/3000/figma-logo-512.png'
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

        .toolsets {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 0.25rem 0.25rem;

            .tool {
                border: solid 1px #bbbbbb;
                border-radius: 0.25rem;
                padding: 0.5rem;
                display: flex;
                align-items: center;
                justify-content: center;

                img {
                    width: 100%;
                    height: 50px;
                    object-fit: contain;
                }
            }
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
        background: #bbbbbb;
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
