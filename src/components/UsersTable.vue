<template>
  <div class="d-flex justify-content-center flex-wrap" style="gap: 40px">
   <users-card  v-for="(user, index) in users" :key="index" :user="user" ></users-card>
  </div>
</template>

<script>
import UsersCard from "./UsersCard.vue";
import users from "../users.json";

export default {
  name: "UsersTable",
  components: {
    UsersCard,
  },
  data() {
    return {
      users,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
