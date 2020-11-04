<template>
  <section>
    <h2>Friends</h2>
    <ul>
      <friend-contact></friend-contact>
    </ul>
  </section>
</template>

<script>
import FriendContact from "@/components/FriendContact";
export default {
  name: "App",
  components: {FriendContact},
  data() {
    return {
      friends: [
        {
          id: "manuel",
          name: "Manuel Lorenz",
          phone: "01234 5678 991",
          email: "manuel@localhost.com",
        },
        {
          id: "julie",
          name: "Julie Jones",
          phone: "09876 543 221",
          email: "manuel@localhost.com",
        },
      ],
    }
  },
}
</script>

<style scoped>

</style>
