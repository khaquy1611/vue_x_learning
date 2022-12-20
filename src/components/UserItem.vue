<template v-if="user">
  <tr>
    <td>
      <img :src="user.avatar" class="mr-2" alt="image" />
      {{ user.name }}
    </td>
    <td>{{ user.age }}</td>
    <td>
      <label v-for="(prgraming,index) in user.programmingLanguage" :key="index" class="badge badge-gradient-primary mr-2">{{ prgraming }}</label>
    </td>
    <td>{{ user.gender }}</td>
    <td>
      <button @click="this.handleRemoveUser(user.id)" type="button" class="mr-2 btn btn-gradient-danger btn-icon-text">
        <i class="mdi mdi-delete btn-icon-prepend"></i> Remove
      </button>
      <button type="button" class="btn btn-gradient-info btn-icon-text">
        <i class="mdi mdi-border-color btn-icon-prepend"></i> Edit
      </button>
    </td>
  </tr>
</template>

<script>
import { mapActions } from "vuex"
export default {
  props: {
    user: {
      type: Object,
      required: true,
    }
  },
  methods: {
    ...mapActions({
      handleRemoveUser: "removeAction",
    }),
  }
};
</script>

<style></style>
