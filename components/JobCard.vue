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
            <a href>View Job</a>
            <a :href="link">Apply Here</a>
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
		margin:25px;
	}

</style>