<template>
  <section class="container">
   
   <UsersTask v-if="home"></UsersTask>
    <user-details-vue v-else></user-details-vue>
  </section>
</template>

<script>
import UserDetailsVue from "./components/UserDetails.vue";
import UsersTask from "./components/Users-Task.vue";

  export default {
    components:{ UsersTask ,UserDetailsVue},
      data() {
          return {
              image: {'backgroundImage': "url(https://via.placeholder.com/150)",'url':"https://via.placeholder.com/150"}
          };
      },
      computed:{
        home(){
                return this.$store.state.home
            }
      }
  };
</script>
