<template>
  <li>
    <h2>{{name}} {{isFav ? "(Favourite)" : ""}}</h2>
    <button @click="toggleFav">Toggle Fav</button>
    <button @click="showDetails">{{detailsAreVisible ? "Hide" : "Show"}} Details</button>
    <ul v-if="detailsAreVisible">
      <li><strong>Phone:</strong>{{phoneNumber}}</li>
      <li><strong>Email:</strong>{{emailAddress}}</li>
    </ul>
    <button @click="triggerDeleteFriend">Delete</button>
  </li>
</template>

<script>
export default {
  name: "FriendContact",
  props: {
    'id': {
      type: String,
      required: true
    },
    'name': {
      type: String,
      required: true,
    },
    'phoneNumber': {
      type: String,
      required: true
    },
    'emailAddress': {
      type: String,
      required: true
    },
    'isFav': {
      type: Boolean,
      required: false,
      default: false
    }
  },
  data() {
    return {
      detailsAreVisible: false,
    }
  },
  methods: {
    showDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
    toggleFav() {
      this.$emit('toggle-fav', this.id);
    },
    triggerDeleteFriend() {
      this.$emit('delete-friend', this.id);
    }
  },
}
</script>
