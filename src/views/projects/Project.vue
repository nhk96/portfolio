<template>
    <div id="project" class="project">
        <div class="title">Project(s)</div>
        <div v-for="(proj, index) in projects" :key="index" class="project-list">
            <div class="project-title">
                <div class="title">{{ proj.title }}
                    <Popover v-show="proj.noFurtherInfo" :id="proj.title">
                        <template #trigger>
                            <div class="no-more-info">!</div>
                        </template>
                        <template #content>
                            <div>
                                No additional information will be disclosed beyond what has already been provided.
                            </div>
                        </template>
                    </Popover>
                </div>
                <div class="project-location">
                    <a v-for="(link, index) in proj.link" :key="index" :href="link.url" target="_blank"
                        rel="noopener noreferrer">
                        <img :src="`/assets/images/icons/${link.title}.png`" :alt="link.title" />

                    </a>
                </div>
            </div>
            <div class="project-description">
                {{ proj.description }}
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
import Popover from '@/components/popover/Popover.vue';

const projects = [
    {
        title: '.svg to .png Converter & Downloader',
        description: 'This project is a simple web application built with Vue.js that enables users to convert .svg files to .png files and download them effortlessly. It is designed to save time by allowing users to drag and drop images from any source, automating the conversion and download process without the need to download images one by one.',
        link: [
            {
                title: 'GitHub',
                url: 'https://github.com/nhk96/downloader'
            },
            {
                title: 'Web',
                url: 'https://downloader.nghokit.com/'
            }
        ]
    },
    {
        title: `Python Language File Translator & Converter`,
        description: `This project is a simple Python script designed to translate text from one language to another. It streamlines the process by allowing users to translate entire files directly into the target language, eliminating the need for manual, line-by-line translation. `,
        link: [
            {
                title: 'GitHub',
                url: ''
            }
        ],
    },
    {
        title: `BOLEHTAK`,
        description: `BOLEHTAK aims to be a platform to ease the confusion faced by Malaysians due to ongoing limitations or SOPs implemented by the government. This platform was designed to allow users to check which businesses and sectors are allowed to operate, along with the rules and SOPs implemented by the government for each state. However, the project ultimately had to be scrapped as the pandemic eased and SOPs were relaxed.`,
        link: [
            {
                title: 'Web',
                url: 'https://bolehtak.nghokit.com/'
            }
        ],
    },
    {
        title: `demoptions`,
        description: `demoptions is a blend of two words: "demo" and "binary options." This marks my first-ever project as a UI/UX Designer in my first full-time job. The project serves as a foundational template, shaping the design framework for the company's future projects.`,
        link: [
            {
                title: 'Download',
                url: ''
            }
        ],
        noFurtherInfo: true
    },
    {
        title: `Fintech `,
        description: `Designed a mobile application for a project titled "Fintech" for my previous employer, tailored for the company's React Native developers.`,
        link: [
            {
                title: 'Download',
                url: ''
            }
        ],
        noFurtherInfo: true
    },
    {
        title: `同济社`,
        description: `同济社 was an icon design project assigned by a client. While the specific usage of the icon remains undisclosed, the client requested that it symbolize a new day and collaboration.`,
        link: [
            {
                title: 'Download',
                url: ''
            }
        ],
        noFurtherInfo: true
    },
    {
        title: `Unnamed e-commerce application`,
        description: `This project was intended to be designed and developed by me and a few friends, with my responsibilities focused on design and frontend development. However, the project was ultimately scrapped as the client opted for other freelancers who offered a more cost-effective solution.`,
        link: [
            {
                title: 'Download',
                url: ''
            }
        ],
        noFurtherInfo: true
    },
    {
        title: `Unnamed food ordering system`,
        description: `This project was intended to be fully designed and developed by me, as it was a unique idea that had not yet been explored locally. Unfortunately, I paused the project for several months due to limited time caused by work commitments. When I returned to it, similar products had already entered the market.`,
        link: [
            {
                title: 'Download',
                url: ''
            }
        ],
        noFurtherInfo: true
    }

];


</script>

<style scoped>
.no-more-info {
    font-size: 0.75rem;
    font-weight: 700;
    color: red;
    border: solid 1px red;
    width: 1rem;
    text-align: center;
    height: 1rem;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 50%;
}

.project {
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

    .project-list {
        display: flex;
        flex-direction: column;


        .project-title {
            font-size: 1.25rem;
            font-weight: 700;
            display: flex;
            justify-content: space-between;
            font-family: var(--secondary-font);
            align-items: center;



            .title {
                display: flex;
                font-family: inherit;
                font-size: inherit;
                font-weight: inherit;
                gap: 10px;

            }

            .project-location {
                display: flex;
                gap: 0.5rem;
                align-items: center;

                a {
                    img {
                        width: 1rem;
                        height: 1rem;
                    }
                }
            }
        }

        .project-location-duration {
            display: flex;
            gap: 0.5rem;
            align-items: center;

            span {
                background: rgba(255, 0, 0, 0.1);
                color: rgba(255, 0, 0, 1);
                font-family: var(--secondary-font);

                font-size: 0.75rem;
                font-weight: 700;
                padding: 0.05rem 0.5rem;
                border-radius: 0.25rem;
            }
        }

        .project-description {
            font-size: 0.75rem;
            margin-top: 0.75rem;




        }
    }
}

@media (max-width: 768px) {
    .project {
        width: 100%;
        padding: 1rem;

        .project-list {
            .project-location-duration {
                gap: 0.25rem;
                flex-direction: column;
                align-items: flex-start;
            }
        }
    }
}
</style>
