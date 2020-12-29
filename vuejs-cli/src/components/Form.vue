<template>
  <div class="form-todo form-group">
    <p>
      <input
        type="text"
        name="author"
        id="author"
        placeholder="Nome"
        class="form-control"
        v-model="name"
      />
    </p>
    <p>
      <textarea
        type="text"
        name="message"
        id="message"
        placeholder="Comentário..."
        class="form-control"
        v-model="message"
      ></textarea>
    </p>
    <p>
      <button v-on:click="addComment" type="submit" class="btn btn-primary">
        Comentar
      </button>
    </p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      message: "",
    };
  },
  methods: {
    addComment() {
      if (this.message.trim() === "") {
        return;
      }

      this.$emit("add-todo", {
        name: this.name,
        message: this.message,
      }),
        (this.name = ""),
        (this.message = "");
    },
  },
};
</script>

<style>
</style>