<template>
    <div id="experiences" class="experience">
        <div class="title">Experience(s)</div>
        <div v-for="(experience, index) in experiences" :key="index" class="experience-list">
            <div class="experience-title">{{ experience.title }}</div>
            <div class="experience-location-duration">

                <div>
                    {{ experience.company }}, {{ experience.location }}
                </div>

                <span class="duration">{{ experience.duration }}</span>
            </div>
            <ul class="experience-description">
                <li v-for="(description, descIndex) in experience.descriptions" :key="descIndex">{{ description }}</li>
            </ul>
        </div>
    </div>
</template>

<script setup lang="ts">
const experiences = [
    {
        title: '“Senior” Front-end Developer',
        company: 'Lock & Lode Sdn. Bhd.',
        location: 'Bangsar South',
        duration: 'March 2020 - Present',
        descriptions: [
            'Led a small team of developers in the development and design of custom React.js and Vue.js components to meet client and user requirements effectively.',
            'Managed the creation of responsive web pages ensuring compatibility across various devices and browsers.',
            'Utilized Adobe Photoshop and Figma to modify and integrate design materials into product development.',
            'Collaborated closely with QA team to address user-reported tickets, providing precise solutions.',
            'Worked in tandem with designers to ensure front-end designs met specified requirements.',
            'Created web design prototypes using Figma, Framer, and Adobe XD, facilitating design iteration and refinement.'
        ]
    },
    {
        title: 'Web Developer, UI/UX Designer & Social Media Marketer',
        company: 'SCACOM Technology Sdn. Bhd.',
        location: 'Puchong',
        duration: 'September 2018 - February 2020',
        descriptions: [
            'Design web UI/UX using Photoshop and Xd or code it straight up bringing the design into real product in ASP.NET using HTML, CSS and JavaScript.',
            'Work closely with support and developer team for any ad-hoc tasks (i.e UI changes, major UI redesign, UI bug fixes) created on Jira making sure all progress is updated.',
            'Using professional tools (i.e Adobe products line-up) to provide graphical design for front-end and marketing usage.',
            'Create and post media on the social media platforms to allow more people to know about the company as well as build up the audience.'
        ]
    },
    {
        title: 'SharePoint Intern',
        company: 'Sistem RKK Sdn. Bhd.',
        location: 'Klang',
        duration: 'August 2017 - October 2017',
        descriptions: [
            'Assisting in SharePoint development creating SharePoint and Nintex workflow as well as SharePoint App-part and Web-part on all SharePoint projects.',
            'Work closely with consultant and clients ensure that end products we deliver are on time and matches client\'s requirement.',
            'Cooperate with support team for troubleshooting any form of technical issues (i.e bugs) whenever there are tickets created by the client.',
            'Communicate with client and update the status of the development and tickets.'
        ]
    },
    {
        title: 'Internship Trainee',
        company: 'Daihatsu (M) Sdn. Bhd.',
        location: 'Shah Alam',
        duration: 'May 2016 - September 2016',
        descriptions: [
            'Providing first-level IT support on both hardware and software and sharing IT tips for Daihatsu (M) Sdn. Bhd. (including its subsidiaries, DMMS) branches all over Malaysia.',
            'In charge of handling and manage company (Windows Server) servers’ load during peak traffic (primarily on beginning of the month and end of the month) ensuring the system are accessible for all the users especially when closing account during month-end.',
            'Work closely with Auto-IT, a powerful dealer management system vendor when there are issues with the software provided by them.',
            'Communicating with ISP (TM Malaysia) for any network related issues ensuring the uptime of the network at 99.9% every month.'
        ]
    }
];
</script>

<style scoped>
.experience {
    width: 50%;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    gap: 2rem;
    height: auto;
    padding: 2rem 0;

    .title {
        font-size: 2rem;
        font-weight: 900;
        font-family: var(--primary-font);
    }

    .experience-list {
        display: flex;
        flex-direction: column;

        .experience-title {
            font-size: 1.25rem;
            font-weight: 700;
            font-family: var(--secondary-font);
        }

        .experience-location-duration {
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

        ul.experience-description {
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
    .experience {
        width: 100%;
        padding: 1rem;

        .experience-list {
            .experience-location-duration {
                gap: 0.25rem;
                flex-direction: column;
                align-items: flex-start;
            }
        }
    }
}
</style>
