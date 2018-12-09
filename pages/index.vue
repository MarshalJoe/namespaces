<script>
import Splash from '~/components/Splash.vue';
import JobCard from '~/components/JobCard.vue';
import jobs from '~/content/jobs.js';

export default {
    components: {
        Splash,
        JobCard
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
    <section>
        <div>
            <Splash/>
            <div class="container">
                <JobCard v-for="(job, index) in jobs" v-bind="job" :key="index" @click.native="toggleCardSelected($event, index)" />
            </div>
        </div>
    </section>
</template>

<style>

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
