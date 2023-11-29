<template>
    <div class="container">
        <div class="row d-flex">
            <img src="./assets/logo.png" style="height: 5rem;">
            <SearchBar @termSearch="onTermSearch"></SearchBar>
        </div>
        <div class="row">
            <VideoDetail v-bind:video="selectedVideo"/>
            <VideoList v-bind:videos="videos" @videoSelect="onVideoSelect"></VideoList>
        </div>
    </div>
</template>
<script>
import axios from 'axios';
import SearchBar from './components/SearchBar';
import VideoList from './components/VideoList';
import VideoDetail from './components/VideoDetail';

export default {
    name: 'App',
    components: {
        SearchBar,
        VideoList,
        VideoDetail
    },
    data() {
        return {
            videos: [],
            selectedVideo: null
        }
    },
    methods: {
        onVideoSelect(video) {
            this.selectedVideo = video
        },
        onTermSearch(searchTerm) {
            axios.get('https://www.googleapis.com/youtube/v3/search',{
                params: {
                    key: process.env.VUE_APP_API_KEY,
                    type: 'video',
                    part: 'snippet',
                    q: searchTerm
                }
            }).then(response => {
                this.videos = response.data.items;
            })
        }
        
    }
};
</script>