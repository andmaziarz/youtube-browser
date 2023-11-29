<template>
    <ul id="list" v-bind:class="ulValue" @click="changeWidth">
        <VideoListItem 
            v-for="video in videos" :key="video.etag"
            v-bind:video="video"
            @videoSelect="onVideoSelect"
        >
        </VideoListItem>
    </ul>
</template>
<script>
    import VideoListItem from './VideoListItem.vue';
    export default{
        name: 'VideoList',
        data() {
            return {
                ulValue : "list-group col-md-12"
            }
        },
        components: {
            VideoListItem
        },
        props: {
            videos: Array
        },
        methods: {
            changeWidth() {
                this.ulValue = "list-group col-md-4"
            },
            onVideoSelect(video) {
                this.$emit('videoSelect', video)
            }
        }
    }
</script>
<style>

</style>