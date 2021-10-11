
<template>
  <div class="row">
    <div class="columns">
      <div class="column is-half is-offset-one-quarter">
        <div class="field is-grouped">
          <p class="control is-expanded">
            <input
              class="input is-primary has-text-centered"
              type="text"
              placeholder="Nova tarefa..."
              v-model="tarefa"
            />
          </p>
          <p class="control">
            <a class="button is-success add-button" @click="sendTask">
              <span class="icon is-small">
                <i class="fa fa-plus"></i>
              </span>
            </a>
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "new-todo",
  data() {
    return {
      tarefa: "",
    };
  },
  methods: {
    sendTask() {
      if (this.tarefa != "") {
        this.$emit("newTask", this.tarefa);
      }
      this.tarefa = "";
    },
  },
};
</script>

<style>
.input {
  border-left: 0;
  border-right: 0;
  border-top: 0;
  border-radius: 0;
  outline: none;
  border-bottom-width: 2px;
  box-shadow: none;
}

.input.is-primary:focus {
  box-shadow: none;
}

.add-button {
  border-radius: 50%;
}
</style>