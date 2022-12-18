<template>
    <v-card elevation="1" width="374" height="100%">
        <v-img :src=products.img>
            <v-btn fab small depressed color="disabled" absolute id="like-icon">
                <v-icon>mdi-cards-heart-outline</v-icon>
            </v-btn>
        </v-img>

        <v-divider></v-divider>

        <v-card-subtitle class="pb-0 text-decoration-line-through text--disabled">
            <div>$ {{products.beforePrice}}</div>
        </v-card-subtitle>

        <v-card-title>
            <v-row align="center" class="mx-0">
                <div id="actual-price">$ {{products.actualPrice}}</div>

                <div class="ms-1 text-uppercase caption" id="discount">
                    {{products.discount}}% off
                </div>
            </v-row>
        </v-card-title>

        <v-card-text class="blue--text pb-0">
            hasta 18 cuotas
        </v-card-text>

        <v-card-text id="product-title">
            {{products.title}}
        </v-card-text>

        <v-card-actions class="justify-center pb-5">
            <v-btn color="disabled" rounded depressed class="text-none px-7">
                <v-icon small class="pr-2">mdi-cart</v-icon>
                Comprar
            </v-btn>
        </v-card-actions>
    </v-card>
</template>


<style>
    #like-icon {
        top: 4px;
        right: 4px;
    }

    #actual-price {
        font-size: 1.7em;
    }

    #discount {
        color: #35a3a8;
    }

    #product-title {
        font-size: 0.9em;
    }
</style>


<script>
  export default {
    name: "ProductCard",
    props: ['products']
  }
</script>