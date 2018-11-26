<script>
import MeetupCard from '~/components/MeetupCard.vue';
import CompanyInquiry from '~/components/CompanyInquiry.vue';
import meetups from '~/content/facebook.js';

export default {
    components: {
        MeetupCard,
        CompanyInquiry
    },

    methods: {
        toggleCardSelected(event, groupIndex) {
            this.meetups[groupIndex].selected = !this.meetups[groupIndex].selected;
        }
    },

    computed: {
        selectedCoursesTitleList() {
            return this.meetups.reduce((accumulator, group) => {
              if(group.selected == true) {
                accumulator.push(group.title);
              }
              return accumulator;
            }, [])
        }
    },

    data: function() {
        return {
            meetups: [
                ...meetups.groups.map((group) => {
                    group["selected"] = false;
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
                <h1>Facebook</h1>
            </div>
            <div class="company__body">
                <MeetupCard v-for="(meetup, index) in meetups" v-bind="meetup" :key="index" @click.native="toggleCardSelected($event, index)" />
            </div>
            <div class="company__inquiry">
                <CompanyInquiry
                    company-name="facebook"
                    info-text="I'm interested in,"
                    :info-list="selectedCoursesTitleList"
                />
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
