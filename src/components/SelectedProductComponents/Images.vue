<template>
    <div>
        <v-container>
            <v-row justify="center">
                <v-card height="545px" width="800px" flat>
                    <v-tabs vertical height="545px">
                        <v-tab v-for="(item, index) of imgThumbnails" :key="index" id="thumbnail">
                                <v-img left :src="require(`../../assets/${item}`)"/>
                        </v-tab>

                        <v-tab-item v-for="(item, index) of imgSrc" :key="index" class="tab-items">
                            <v-card flat class="h-100">
                                <a id="img-active" class="d-flex" @click="overlay = !overlay">
                                    <v-img :src="item" min-width="30%" max-height="500px" min-height="450px" contain class="d-inline flex-none"/>
                                </a>
                            </v-card>
                        </v-tab-item>
                    </v-tabs>
                </v-card>
            </v-row>
        </v-container>

        <template>
            <v-overlay :value="overlay">
                <v-container fluid class="px-10 py-10">
                        <v-btn @click="overlay = false" absolute id="close-icon" depressed>
                            <v-icon small>mdi-close</v-icon>
                        </v-btn>

                        <v-carousel hide-delimiters height="auto">
                            <v-carousel-item v-for="(item, index) in imgSrc" :key="index" :src="item" class="height-auto"></v-carousel-item>
                        </v-carousel>

                </v-container>
            </v-overlay>
        </template>
    </div>
</template>


<style>
    #img-active {
        width: 100%;
        background-color: white;
        justify-content: center;
        height: 100%;
        align-items: center;
    }

    .tab-items {
        height: 545px;
    }

    #close-icon {
        top: -10px;
    }

    .h-100 {
        height: 100%;
    }

    #thumbnail {
        height: 136px;
        width: 132px;
        border: 1px solid rgba(0, 0, 0, 0.05);
    }
</style>


<script>
    export default {
        name: "ImagesVue",

        data: () => ({
            overlay: false,

            imgThumbnails: [
                "thumbnail-01.png",
                "thumbnail-02.png",
                "thumbnail-03.png",
                "thumbnail-04.png"
            ],

            imgSrc: [
                "https://foschia.com.ar/static/uploads/products/webp/imIqk4qF2eygJQUGAHuPjbIR38nb78HKnmToj-bn6Iqms6iJ-0a1aQfM2pz0gZIpYNCGMMqtNAKtGo8OC8fhn7N7lav_Id65.webp?x=1670858102",
                "https://foschia.com.ar/static/uploads/products/webp/imIqk4qF2eygJQUGAHuPjbIR38nb78HKnmToj-bn6Iqms6iJ-0a1aWygguIlajR7Beheynis8iH3fi0O_zyYHd_gELeac0xz.webp?x=1670858103",
                "https://foschia.com.ar/static/uploads/products/webp/imIqk4qF2eygJQUGAHuPjbIR38nb78HKnmToj-bn6Iqms6iJ-0a1aRkO5ROIPwTOuvtFzTcK-vsy-tGNHZ1vjxJl3O9nFMdM.webp?x=1670858103",
                "https://foschia.com.ar/static/uploads/products/webp/imIqk4qF2eygJQUGAHuPjbIR38nb78HKnmToj-bn6Iqms6iJ-0a1aaV8lVpJ0gksKo9fEYzmCTeeVAlOjbXsiFMUSIB-9D_B.webp?x=1670858103"
            ]
        })
    }
</script>