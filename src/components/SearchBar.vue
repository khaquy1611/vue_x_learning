<template>
  <div class="form-group">
    <div class="input-group">
      <input
        type="text"
        class="form-control"
        placeholder="Recipient's username"
        aria-label="Recipient's username"
        aria-describedby="basic-addon2"
        v-model="searchName"
      />
      <div class="input-group-append">
        <button @click="handlerClickSearch" class="btn btn-sm btn-gradient-primary" type="button">
          Search
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import { mapActions } from 'vuex';
export default {
  state() {
    return {
       searchName: ""
    }
  },
  methods: {
    handlerClickSearch() {
      this.clickSearch(this.searchName);
    },
    ...mapActions({
      clickSearch : 'setSearchNameAction' // map `this.add()` to `this.$store.dispatch('increment')`
    })
  }
};
</script>

<style></style>
