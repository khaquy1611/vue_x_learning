<template>
  <div class="card">
    <div class="card-body">
      <form class="forms-sample">
        <div class="form-group">
          <label for="username">Username</label>
          <input
            type="text"
            class="form-control"
            id="username"
            placeholder="Username"
            v-model="user.name"
          />
        </div>
        <div class="form-group">
          <label for="age">Age</label>
          <input
            type="number"
            class="form-control"
            id="age"
            placeholder="Age"
            v-model="user.age"
          />
        </div>
        <div class="form-group">
          <label for="avatar">Avatar</label>
          <input
            type="text"
            class="form-control"
            id="avatar"
            placeholder="avatar"
            v-model="user.avatar"
          />
        </div>
        <div class="form-group">
          <label for="">Programming Language : </label>
          <div class="form-row-flex">
            <div class="form-check">
              <label class="form-check-label">
                <input
                  v-model="user.programmingLanguage"
                  value="JavaScript"
                  type="checkbox"
                  class="form-check-input" />
                JavaScript <i class="input-helper"></i
              ></label>
            </div>
            <div class="form-check">
              <label class="form-check-label">
                <input
                  v-model="user.programmingLanguage"
                  value="Java"
                  type="checkbox"
                  class="form-check-input" />
                Java <i class="input-helper"></i
              ></label>
            </div>
            <div class="form-check">
              <label class="form-check-label">
                <input
                  v-model="user.programmingLanguage"
                  value="PHP"
                  type="checkbox"
                  class="form-check-input" />
                PHP <i class="input-helper"></i
              ></label>
            </div>
            <div class="form-check">
              <label class="form-check-label">
                <input
                  v-model="user.programmingLanguage"
                  value="Python"
                  type="checkbox"
                  class="form-check-input" />
                Python <i class="input-helper"></i
              ></label>
            </div>
            <div class="form-check">
              <label class="form-check-label">
                <input
                  v-model="user.programmingLanguage"
                  value="C#"
                  type="checkbox"
                  class="form-check-input" />
                C# <i class="input-helper"></i
              ></label>
            </div>
            <div class="form-check">
              <label class="form-check-label">
                <input
                  v-model="user.programmingLanguage"
                  value="C/C++"
                  type="checkbox"
                  class="form-check-input" />
                C/C++ <i class="input-helper"></i
              ></label>
            </div>
          </div>
        </div>
        <div class="form-group">
          <label for="">Gender : </label>
          <div class="d-flex">
            <div class="form-check mr-3">
              <label class="form-check-label">
                <input
                  v-model="user.gender"
                  type="radio"
                  class="form-check-input"
                  name="gender"
                  id="gender"
                  value="Nam" />
                Nam <i class="input-helper"></i
              ></label>
            </div>
            <div class="form-check mr-3">
              <label class="form-check-label">
                <input
                  v-model="user.gender"
                  type="radio"
                  class="form-check-input"
                  name="gender"
                  id="gender"
                  value="N???" />
                N??? <i class="input-helper"></i
              ></label>
            </div>
            <div class="form-check mr-3">
              <label class="form-check-label">
                <input
                  v-model="user.gender"
                  type="radio"
                  class="form-check-input"
                  name="gender"
                  id="gender"
                  value="Kh??c" />
                Kh??c <i class="input-helper"></i
              ></label>
            </div>
          </div>
        </div>
        <div class="form-group row">
          <label class="col-sm-3 col-form-label">Type User : </label>
          <div class="col-sm-9">
            <select v-model="user.type" class="form-control">
              <option value="" selected disabled hidden>-- Ch???n Lo???i --</option>
              <option value="ADMIN">Admin</option>
              <option value="CLIENT">Client</option>
            </select>
          </div>
        </div>
        <div class="form-group">
          <label for="description">Description</label>
          <textarea
            v-model="user.description"
            class="form-control"
            id="description"
            rows="4"
          ></textarea>
        </div>
        <button
          @click.prevent="handleAddUser(user)"
          type="submit"
          class="btn btn-gradient-primary mr-2"
        >
          Submit
        </button>
        <button class="btn btn-light">Cancel</button>
      </form>
    </div>
  </div>
</template>

<script>
import { mapActions } from "vuex";
export default {
  data() {
    return {
      user: {
        name: "",
        age: "",
        avatar: "",
        programmingLanguage: [],
        gender: "",
        type: "",
        description: "",
      },
    };
  },
  methods: {
    ...mapActions({
      handleAddUser: "addUserAction",
    }),
  },
};
</script>

<style>
.form-row-flex {
  display: flex;
  justify-content: space-around;
  align-items: center;
}
</style>
