<template>
  <form @submit.prevent="triggerAddContact">
    <div>
      <lable>Name</lable>
      <input type="text" v-model="enteredName">
    </div>
    <div>
      <lable>E-Mail</lable>
      <input type="text" v-model="enteredEmail">
    </div>
    <div>
      <lable>Add Contact</lable>
      <input type="text" v-model="enteredPhone">
    </div>
    <div>
      <button>Add Contact</button>
    </div>
  </form>
</template>

<script>
export default {
  name: "NewFriend",
  emits: ['add-contact'],
  data() {
    return {
      enteredName: "",
      enteredEmail: "",
      enteredPhone: "",
    }
  },
  methods: {
    triggerAddContact() {
      this.$emit(
        'add-contact',
        this.enteredName,
        this.enteredPhone,
        this.enteredEmail
      );
    }
  }
}
</script>
