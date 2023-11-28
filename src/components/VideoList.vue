<template>
    <ul class="list-group">
        <VideoListItem 
            v-for="video in videos" :key="video.etag"
            v-bind:video="video"
        >
        </VideoListItem>
    </ul>
</template>
<script>
import VideoListItem from './VideoListItem.vue';
    export default{
        name: 'VideoList',
        components: {
            VideoListItem
        },
        props: {
            videos: Array
        }
    }
</script>
<style>

</style>