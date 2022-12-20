<template>
  <tbody>
    <user-item 
    v-for="item in userListSearchName" 
    :key="item.id"
    :user="item"
    ></user-item>
  </tbody>
</template>

<script>
import UserItem from "./UserItem.vue";
import { mapState, mapGetters } from 'vuex';
export default {
  components: {
    UserItem,
  },
  computed: {
    ...mapState({
      userList: (state) => state.userList,
    }),
    ...mapGetters({
      userListByBoy: 'userListBoy',
      userListSearchName: 'userListBySearchName'
    })
  }
};

</script>

<style></style>
