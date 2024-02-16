<script>
import { ytVideos } from '/src/data/_video'
export default {
    name: 'VideoPlayer',
    data: () => ({
        ytVideos,
        videoId: 1,
        videoUrl: 'https://www.youtube.com/watch?v=ebHd_3QJNBA',
        videoTitle: '',
        videoImage: ''
    }),
    computed: {
        videoThumb() {
            return `${this.videoUrl}/lqdefault.jpg`
        }

    },
    methods: {
        displayClickedVideo(videoid, videourl, videotitle) {
            this.videoId = videoid;
            this.videoUrl = videourl;
            this.videoTitle = videotitle;
            this.videoImage = this.videoImage

            console.log(this.videoId, this.videoUrl, this.videoTitle,)





        }

    }
}
</script>

<template>
    <div id="main">
        <div id="video-player" class="container">
            <div class="row d-flex">
                <div id="video-container" class="col-8">
                    <iframe width="1792" height="864" src="https://www.youtube.com/embed/ebHd_3QJNBA"
                        title="Sword of the Stranger fight scene" frameborder="0"
                        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
                        allowfullscreen></iframe>

                </div>
                <div id="video-list-section" class="col-4">
                    <div id="videolist-header" class="d-flex justify-content-start align-items-center p-2">
                        <i class="fa-solid fa-play ps-4"></i>
                        <div class="ps-4">
                            <p class="h6 mb-1">Video Playlist</p>
                            <p class="m-0">{{ videoId }}/7 videos</p>
                        </div>
                    </div>
                    <div id="video-list">
                        <button @click="displayClickedVideo(video.id, video.url, video.title)" v-for="video in ytVideos"
                            id="video-card" class="d-flex justify-content-start align-items-center p-2">
                            <div id="video-id" class="d-flex justify-content-center align-items-center">
                                <p>{{ video.id }}</p>
                            </div>
                            <div id="video-thumb">
                                <img :src="video.image" alt="thumbnail">
                            </div>
                            <div id="video-title">
                                <p>{{ video.title }}</p>
                            </div>
                        </button>

                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss">
@use '/src/assets/scss/style.scss' as *;

#main {
    padding-top: 50px;
    padding-bottom: 50px;

    p {
        margin: 0;
        padding: 0;
    }

    #video-player {
        min-height: 550px;
        background-color: gray;

        .row {
            height: 100%;

            #video-container {
                background-color: chocolate;
                height: 600px;
                padding: 0;

                iframe {
                    width: 100%;
                    height: 100%;
                }

            }

            #video-list-section {
                background-color: cornflowerblue;
                height: 600px;
                padding: 0;

                #videolist-header {
                    width: 100%;
                    height: 100px;
                    background-color: rgb(59, 59, 59);
                    color: white;

                    i {
                        font-size: 2rem;
                    }
                }

                #video-list {
                    width: 100%;
                    max-height: calc(100% - 100px);
                    background-color: darkcyan;
                    overflow: scroll;

                    #video-card {
                        width: 100%;
                        height: 110px;
                        background-color: rgb(233, 233, 233);
                        gap: 10px;
                        border: 0;

                        #video-id {
                            background-color: rgb(75, 75, 75);
                            min-width: 25px;
                            min-height: 25px;
                            border-radius: 5px;
                            color: white;
                            font-size: 0.8rem;
                            transition: all .2s ease;
                        }

                        img {
                            max-width: 70px;
                            border-radius: 10px;
                        }
                    }

                    #video-card:hover #video-id {
                        background-color: rgb(184, 4, 4);
                    }

                    #video-card:hover #video-title {
                        color: rgb(201, 0, 0);
                    }
                }


            }

        }

    }
}
</style>

