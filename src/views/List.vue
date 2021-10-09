<template>
  <div>
    <input v-model="newContact" placeholder="Name" type="text" />
    <button @click="addContact">Add Contact</button>
    <button @click="sortContacts">Sort Contact</button>

    <transition-group name="slide-up" tag="ul" appear>
      <li v-for="(contact, index) in contacts" :key="index">
        {{ contact }}
      </li>
    </transition-group>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newContact: '',
      contacts: ['Beau Thabeast', 'Cindy Rella', 'Alice Wunderlind'] // Initial contact list
    }
  },
  methods: {
    addContact() {
      this.contacts.push(this.newContact) // Pushes the newContact into our contacts list
      this.newContact = '' // Resets our newContact
    },
    sortContacts() {
      this.contacts.sort() // Sorts the list alphabetically based on the 1st letter of the person's first name
    }
  }
}
</script>

<style scoped>

li {
  list-style: none;
}

</style>
