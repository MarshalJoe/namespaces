<template>
    <div :class="'text-left job-card ' + computedClasses">
        <div class="job-card__header">
            <div class="job-card__header_text">
                <h3 class="job-card__title">{{ title }}</h3>
                <p>{{ company }}</p>
            </div>
        </div>
        <p class="job-card__description" v-html="description"></p>
        <div class=" text-left job-card__next-meetup">
            <a class="button-clear" :href="'/jobs/' + jobid">View</a>
            <a class="button-clear" :href="link">Apply</a>
        </div>
    </div>
</template>

<script>

export default {

    computed: {
        computedClasses() {
            return this.selected ? "meetup-card__selected_true" : ""
        },
    },

    props: {
        jobid: {
            default: "",
            type: String
        },

        title: {
            default: "",
            type: String
        },

        type: {
            default: "",
            type: String
        },

        link: {
            default: "members",
            type: String
        },

        description: {
            default: "",
            type: String
        },

        location: {
            default: "",
            type: String
        },

        company: {
            default: "",
            type: String
        },

        selected: {
            default: false,
            type: Boolean
        }
    }
}
</script>

<style lang="scss">
	.job-card {
		margin:25px 0 25px 0;
	}

</style>