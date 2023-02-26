<template>
    <div class="post-list">
        <div v-for="post in posts" :key="post.id">
            <SinglePost :post="post"/>
        </div>
    </div>
</template>

<script>
import SinglePost from "./SinglePost.vue"
export default {
    name: 'Comp3BlogPostList',
    props: ['posts'],
    components: { SinglePost },
    setup(props) {
        console.log(props.posts)
    }
}
</script>

<style lang="scss" scoped>

</style>