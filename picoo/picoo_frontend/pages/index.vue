<template>
  <div class="container">
    <main>
      <label for="file">
        <input type="file" id="file" @change="fileSelected" />
      </label>
      
      <label for="title">
        画像タイトル
        <input type="text" placeholder="画像タイトル" id="title" name="title" v-model="newTitle">
      </label>

      <textarea name="post_comment" id="" cols="30" rows="11" placeholder="投稿コメント" v-model="newPostComment"></textarea>
      <label for="tag">
        タグ名
        <input type="text" placeholder="タグ名" id="tag" name="tag" v-model="newTag">
      </label>
      <button @click="fileUpload">投稿する</button>
    </main>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        newTitle: "",
        newPostComment: "",
        newTag: "",
        picture: "",
      };
    },

    methods: {
      fileSelected(event) {
        this.picture = event.target.files[0]
      },

      async fileUpload() {
        // const formData = new FormData();
        // formData.append('picture', this.picture)
        const formData = {
          title: this.newTitle,
          post_comment: this.newPostComment,
          tag: this.newTag,
          picture: this.picture,
        };
        await this.$axios.post("http://127.0.0.1:8000/", formData);
      }
    },
  }

</script>

<style>
</style>