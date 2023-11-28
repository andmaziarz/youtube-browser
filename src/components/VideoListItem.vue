<template>
    <li class="list-group-item media">
        <img v-bind:src="thumbnailUrl" class="mr-3"/>
        <div class="media-body">
            {{ videoTitle }}
        </div>
    </li>
</template>

<script>
export default{
    name: 'VideoListItem',
    props: ['video'],
    computed: {
        thumbnailUrl(){
            return this.video.snippet.thumbnails.default.url
        },
        videoTitle(){
            return this.video.snippet.title
        }
    }
}
</script>

<style scoped>
li {
    display: flex;
    cursor: pointer;
}
li:hover{
    background-color: #eee;
}
</style>