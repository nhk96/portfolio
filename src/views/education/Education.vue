<template>
    <div id="education" class="education">
        <div class="title">Education(s)</div>
        <div v-for="(edu, index) in education" :key="index" class="education-list">
            <div class="education-title">{{ edu.title }}</div>
            <div class="education-location-duration">
                {{ edu.institution }}, {{ edu.location }}
                <span>{{ edu.duration }}</span>
            </div>
            <ul class="education-description">
                <li>CGPA: {{ edu.cgpa }}</li>
            </ul>
        </div>
    </div>
</template>

<script setup lang="ts">
const education = [
    {
        title: 'Degree in Software Engineering',
        institution: 'Asia Pacific University',
        location: 'Bukit Jalil, Malaysia',
        duration: 'September 2016 - August 2018',
        cgpa: '2.90'
    },
    {
        title: 'High School Diploma',
        institution: 'Example High School',
        location: 'Example Town',
        duration: 'September 2011 - June 2015',
        cgpa: '2.90'
    }
];
</script>

<style scoped>
.education {
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

    .education-list {
        display: flex;
        flex-direction: column;

        .education-title {
            font-size: 1.25rem;
            font-weight: 700;
            font-family: var(--secondary-font);
        }

        .education-location-duration {
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

        ul.education-description {
            font-size: 0.75rem;
            margin-top: 0.75rem;
            list-style-type: '-';
            padding-inline-start: 0.25rem;

            li {
                padding-inline-start: 0.75rem;
                padding-bottom: 0.25rem;
            }
        }
    }
}

@media (max-width: 768px) {
    .education {
        width: 100%;
        padding: 1rem;

        .education-list {
            .education-location-duration {
                gap: 0.25rem;
                flex-direction: column;
                align-items: flex-start;
            }
        }
    }
}
</style>
