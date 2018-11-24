<template>
  <div class="meetup-card">
    <h2 class="text-center">{{ title }}</h2>
    <h3 class="text-left">{{ sizeMembers }} </h3>
    <p class="text-left" v-html="description"></p>
    <div class="meetup-card__next-meetup">
      <p>{{ nextMeetup }}</p>
    </div>
  </div>
</template>

<script>

export default {
  
  computed: {
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
    }
  }
}
</script>

<style>

</style>
