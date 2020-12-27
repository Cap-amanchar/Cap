<template lang="pug">
div
  .col-large.push-top(v-for="thread in threads")
    h1 {{thread.title}}
    .post-list
     .post(v-for="postId in thread.posts")
      .user-info
       a.user-name(href="#") {{users[posts[postId].userId].name}}
       a(href="#")
         img.avatar-large(:src="users[posts[postId].userId].avatar" alt="")
       .desktop-only.text-small 107 posts
      .post-content
        div {{posts[postId].text}}
      .post-date.text-faded {{posts[postId].publishedAt}}
</template>
<script>
import ForumData from "../data.json" ;
export default {

  name: 'HelloWorld',
  data() {
    return {
      threads: ForumData.threads,
      posts: ForumData.posts,
      users:ForumData.users
    }
  }
}
</script>
