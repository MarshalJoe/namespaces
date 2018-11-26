<template>
    <div :class="'text-left meetup-card ' + computedClasses">
        <div class="meetup-card__header">
            <img :src="logo" class="meetup-card__logo"/>
            <div class="meetup-card__header_text">
                <h2 class="meetup-card__title">{{ title }}</h2>
                <h3 class="meetup-card__size">{{ sizeMembers }} </h3>
            </div>
        </div>
        <p class="meetup-card__description" v-html="description"></p>
        <div class=" text-center meetup-card__next-meetup">
            <p>{{ nextMeetup }}</p>
        </div>
    </div>
</template>

<script>

export default {

    computed: {
        computedClasses() {
            return this.selected ? "meetup-card__selected_true" : ""
        },

        sizeMembers() {
            return this.size.toString() + " " + this.members;
        }
    },

    props: {
        title: {
            default: "",
            type: String
        },

    size: {
        default: 0,
        type: Number
    },

    logo: {
        default: "",
        type: String
    },

    members: {
        default: "members",
        type: String
    },

    description: {
        default: "",
        type: String
    },

    nextMeetup: {
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

.meetup-card {
    margin: 15px;
    transition: 1s;
    border: 1px solid lightgrey;
    box-shadow: 2px 2px 2px 1px rgba(0, 0, 0, 0.2);

    &.meetup-card__selected_true {
        background-color: skyblue;
    }
}

.meetup-card__header {
    display: table;
    padding:25px;
}

.meetup-card__logo {
    height: auto;
    width: 75px;
    margin-right: 10px;
    background-repeat: no-repeat;
    background-size: cover;
}

.meetup-card__header_text {
    display: table-cell;
    vertical-align: middle;
}

.meetup-card__size {
    font-size: 1rem;
    color:gray;
}

.meetup-card__description {
    padding-left: 25px;
    padding-right: 25px;
}

.meetup-card__next-meetup {
    height:50px;
    line-height: 50px;
    font-size: 1rem;
    text-transform: uppercase;
    color:white;
    background-color: #3b5998;
}
</style>
