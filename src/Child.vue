<template>
  <div>
    <button @click="emitFetchUsersEvent">Child Button</button>
    <span v-if="loading">fetching users...</span>
    <br></br>
    <span v-if="users">
      Got the users
    </span>
  </div>
</template>

<script>
export default {
  name: 'Child',
  data() {
    return {
      loading: false,
      users: null,
    };
  },
  methods: {

    emitFetchUsersEvent() {
      this.loading = true;
      this.users = null;

      // EXERCISE 01: CHILD TO PARENT EVENT
      this.    // <- ANSWER
      ('fetchUsers', (res) => {
        this.loading = false;
        this.users = res;
      });
    },
  },
};
</script>

<style>
div {
  display: grid;
  place-items: center;
}
</style>
