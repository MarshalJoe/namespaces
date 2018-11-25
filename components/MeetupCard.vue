<template>
  <div class="text-left meetup-card">
    <div class="meetup-card__header">
      <div class="meetup-card__logo"></div>
      <div class="meetup-card__header_text">
          <h2 class="meetup-card__title">{{ title }}</h2>
          <h3 class="meetup-card__size">{{ sizeMembers }} </h3>
      </div>
    </div>
    <p v-html="description"></p>
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

.meetup-card {
  padding: 25px;
  transition: 1s;  
  border: 1px solid lightgrey;
  cursor: pointer;
}

.meetup-card:hover {
  box-shadow: 3px 3px 2px 1px rgba(0, 0, 0, 0.3);;
}

.meetup-card__header {
  display: table;
  padding:10px;
}

.meetup-card__logo {
  height: 75px;
  width: 75px;
  margin-right: 10px;
  background-image: url("/images/react-logo.png");
  background-repeat: no-repeat;
  background-size: cover;
}

.meetup-card__header_text {
  display: table-cell;
  vertical-align: middle;
}

.meetup-card__size {
  font-size:1rem;
  color:gray;
}

.meetup-card__next-meetup {
  font-size: .85rem;
  text-transform: uppercase;
  color: #3b5998;
}

</style>
