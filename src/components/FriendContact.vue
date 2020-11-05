<template>
  <li>
    <h2>{{name}} {{favFriend ? "(Favourite)" : ""}}</h2>
    <button @click="toggleFav">Toggle Fav</button>
    <button @click="showDetails">{{detailsAreVisible ? "Hide" : "Show"}} Details</button>
    <ul v-if="detailsAreVisible">
      <li><strong>Phone:</strong>{{phoneNumber}}</li>
      <li><strong>Email:</strong>{{emailAddress}}</li>
    </ul>
  </li>
</template>

<script>
export default {
  name: "FriendContact",
  props: {
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
      favFriend: this.isFav
    }
  },
  methods: {
    showDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
    toggleFav() {
      this.favFriend = !this.favFriend;
    }
  },
}
</script>
