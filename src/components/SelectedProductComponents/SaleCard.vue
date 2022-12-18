<template>
    <div class="pb-5">
        <div>
            <v-btn fab small depressed color="disabled" absolute id="icon-like" class="btn-icons">
                <v-icon>mdi-cards-heart-outline</v-icon>
            </v-btn>

            <v-btn fab small depressed color="disabled" absolute id="icon-share" class="btn-icons">
                <v-icon>mdi-share-variant</v-icon>
            </v-btn>
        </div>

        <v-card flat class="px-3">
            <v-card-subtitle>
                <div>
                    <a class="text--blue" href="https://foschia.com.ar/shop/griferias">
                        Griferías
                    </a>
                    >
                    <a class="text--blue" href="https://foschia.com.ar/shop/griferias-griferias-para-cocina">
                        Griferías Para Cocina
                    </a>
                    >
                    <a class="text--blue" href="https://foschia.com.ar/shop/griferias-griferias-para-cocina-monocomando">
                        Monocomando
                    </a>
                </div>
            </v-card-subtitle>

            <v-card-title>
                <v-row align="center" class="mx-0">
                    <div id="title"> 
                        {{title}}
                    </div>

                    <div class="ms-1 text--disabled caption">
                        {{serial}}
                    </div>
                </v-row>
            </v-card-title>

            <v-card-subtitle class="pb-0 text-decoration-line-through text--disabled pt-8">
                <div>$ {{lastPrice}}</div>
            </v-card-subtitle>

            <v-card-title>
                <v-row align="center" class="px-3 pb-8">
                    <div id="price">$ {{actualPrice}}</div>

                    <div class="ms-1 text-uppercase" id="discount">
                        {{discount}}% off
                    </div>
                </v-row>
            </v-card-title>

            <v-card-subtitle id="description">
                <div class="pb-4">
                    <v-icon color="#222" small>mdi-check-bold</v-icon>
                    Stock disponible
                </div>

                <div class="pb-4">
                    <v-icon color="#222" small>mdi-credit-card-outline</v-icon>
                    Planes ahora 3, 6, 12 y 18 
                </div>

                <div class="pb-4">
                    <v-icon color="#222" small>mdi-information</v-icon>
                    Disponible para 
                    <a class="font-weight-bold" href="https://foschia.com.ar/acopio">Acopio en depósito</a>
                </div>
            </v-card-subtitle>

            <v-card-actions class="justify-center pb-0">
                <v-form class="text-center">
                    <v-container>
                        <v-row justify="center" id="row-quantity">
                            <v-col cols="3" class="py-0 px-0">
                                <v-btn text outlined depressed id="btn-quantity" @click="quantity > 1 ? quantity-=1 : quantity">
                                    <v-icon>mdi-minus</v-icon>
                                </v-btn>
                            </v-col>

                            <v-col cols="2" class="py-0 px-0">
                                <v-text-field :value="quantity" id="input-quantity"></v-text-field>
                            </v-col>

                            <v-col cols="3" class="py-0 px-0">
                                <v-btn text outlined depressed id="btn-quantity"  @click="quantity < stock ? quantity+=1 : quantity">
                                    <v-icon>mdi-plus</v-icon>
                                </v-btn>
                            </v-col>
                        </v-row>
                    </v-container>
                </v-form>
            </v-card-actions>

            <v-card-subtitle id="stock" class="pt-0 text-center">
                {{stock}} disponibles
            </v-card-subtitle>

            <v-card-actions class="justify-center pt-0">
                <v-btn color="#007AC1" depressed class="text-none" dark block large>
                    <v-icon small class="pr-2">mdi-cart</v-icon>
                    Comprar ahora
                </v-btn>
            </v-card-actions>
        </v-card>
    </div>
</template>


<style>
    a {
        text-decoration: none;
    }

    .btn-icons {
        scale: .9;
    }

    #icon-like {
        top: 5px;
        right: 5px;
    }

    #icon-share {
        top: 50px;
        right: 5px;
    }

    #title {
        line-height: 1.1em;
        font-size: 1.8em;
        word-break: break-word;
        font-weight: 100;
    }

    #price {
        font-size: 2.7em;
        font-weight: 100;
    }

    #discount {
        font-size: 1.1em;
        color: #35a3a8;
    }

    #description {
        color: #222;
        font-size: 0.9em;
    }

    #row-quantity {
        align-items: center;
    }

    #input-quantity {
        text-align: center;
        color: #999;
        border-bottom: 1px solid #ddd;
        font-size: 1.2em;
    }

    #btn-quantity {
        border: 1px dotted #007AC1;
        color: #007AC1;
    }

    #stock {
        color: rgba(34, 34, 34, .8);
        font-size: 0.9em;
    }
</style>


<script>
    export default {
        name: "SaleCardVue",

        data: () => ({
            title: "Grifería De Cocina Ultragrif Jack Steel Monocomando",
            serial: "FOS-141574",
            lastPrice: 16.008,
            actualPrice: 13.127,
            discount: 18,
            stock: 71,
            quantity: 1
        })
    }
</script>