<script>
import JobCard from '~/components/JobCard.vue';
import jobs from '~/content/jobs.js';

export default {
    components: {
        JobCard,
    },

    data: function() {
        return {
            jobs: [
                ...jobs.groups.map((group) => {
                    group["description"] = group["description"].replace(/<(?:.|\n)*?>/gm, '').substring(0,250) + "...";
                    return group;
                })
            ]
        };
    }
}
</script>

<template>
    <section class="container">
        <div>
            <div class="company__hero">
                <h1>Junior Dev Jobs</h1>
                <h2>Find Your First Dev Job</h2>
            </div>
            <div class="company__body">
                <JobCard v-for="(job, index) in jobs" v-bind="job" :key="index" @click.native="toggleCardSelected($event, index)" />
            </div>
        </div>
    </section>
</template>

<style>

.container {
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
}

.title {
    font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
    display: block;
    font-weight: 300;
    font-size: 100px;
    color: #35495e;
    letter-spacing: 1px;
}

.subtitle {
    font-weight: 300;
    font-size: 42px;
    color: #526488;
    word-spacing: 5px;
    padding-bottom: 15px;
}

.links {
    padding-top: 15px;
}
</style>
