<template>
    <v-container class="mb-10 mx-auto px-auto">
        <v-row justify="center">
            <v-col>
                <h4 id="title">También te puede interesar</h4>
            </v-col>
        </v-row>

        <v-row justify="center">
            <v-col cols="3" v-for="(item, index) of products" :key="index" class="d-flex justify-center">
                <a class="text-none" id="product-card" :href="item.link" target="_blank">
                    <ProductCard v-bind:products="item"/>
                </a>
            </v-col>
        </v-row>
    </v-container>
</template>


<style>
    #title {
        font-size: 1.7rem;
        font-weight: 600;
        line-height: 1.5em;
        color: #222;
    }

    #product-card {
        max-width: 100%;
    }
</style>


<script>
    import ProductCard from '../components/ProductCard/ProductCard.vue';
    
    export default {
        name: "ProductsVue",

        components: {
            ProductCard
        },

        data () {
            return {
                products: [
                    {
                        img: "https://foschia.com.ar/static/uploads/products/webp/imIqk4qF2eygJQUGAHuPjbIR38nb78HKnmToj-bn6IqSWOx8MXUAqJ3pnP1UU-sup9xfhGfOggrTdjTNA9hlM7zDYG4672Og_smsq.webp?x=1627203206",
                        beforePrice: 79.891,
                        actualPrice: 47.935,
                        discount: 40,
                        title: "Grifería de Cocina Monocomando Vasser",
                        link: "https://foschia.com.ar/product/griferia-de-cocina-monocomando-vasser-lyra/kewnMK9LYbE-iGI03ne4dQ"
                    },
                    {
                        img: "https://foschia.com.ar/static/uploads/products/webp/imIqk4qF2eygJQUGAHuPjbIR38nb78HKnmToj-bn6Ipzoqq_4iDjkzLircgOeKY2ipPyiQ8YGwplQONVQTfvB4tugj6H5efj_smsq.webp?x=1592323672",
                        beforePrice: 242.109,
                        actualPrice: 198.529,
                        discount: 18,
                        title: "Grifería Monocomando Cocina Bonnie 411/H1",
                        link: "https://foschia.com.ar/product/griferia-monocomando-cocina-fv-bonnie-411h1/zNmgovBm7b2xxphzNGASlg"
                    },
                    {
                        img: "https://foschia.com.ar/static/uploads/products/webp/imIqk4qF2eygJQUGAHuPjbIR38nb78HKnmToj-bn6IqQmp685dozMgWmkS4SNiul3hlcjmqqf4GtltpTCYB8CoqR20Epy4x4_smsq.webp?x=1669913125",
                        beforePrice: 72.850,
                        actualPrice: 59.737,
                        discount: 18,
                        title: "Grifería de Cocina Monocomando Ultragrif Cooper",
                        link:"https://foschia.com.ar/product/griferia-de-cocina-monocmando-ultragrif-cooper/MN8dqRopCECVbJCK--AOqw"
                    },
                    {
                        img: "https://foschia.com.ar/static/uploads/products/webp/imIqk4qF2eygJQUGAHuPjbIR38nb78HKnmToj-bn6Iq4DeIV3YQh2xlTOdjYrS8tvFDRUrT-YDgA8qaIfQN0_wPB8rJLHdhf_smsq.webp?x=1663339203",
                        beforePrice: 129.225,
                        actualPrice: 98.584,
                        discount: 18,
                        title: "Grifería Monocomando Cocina Black Hidromet",
                        link:"https://foschia.com.ar/product/griferia-monocomando-cocina-black-hidromet-discovery-910/aVocehylFz34vxGUBj-1sA"
                    }
                ]
            }
        }
    }
</script>