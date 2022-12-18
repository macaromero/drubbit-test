<template>
    <v-footer dark color="black" padless>
        <v-container class="pt-10">
            <v-row no-gutters justify="center">
                <v-col cols="2">
                    <v-card tile flat color="transparent">
                        <v-img src="../assets/logo-footer.webp" width="70%"/>
                    </v-card>
                </v-col>

                <v-col cols="2">
                    <v-card tile flat color="transparent">
                        <v-card-actions class="py-0">
                            <v-btn text id="btn-links" href="mailto:info@foschia.com.ar">
                                <v-icon dense class="pr-1">mdi-email</v-icon>
                                {{firstCol[0]}}
                            </v-btn>
                        </v-card-actions>

                        <v-card-actions class="py-0">
                            <v-btn text id="btn-links" href="tel:+5401160123758">
                                <v-icon dense class="pr-1">mdi-phone</v-icon>
                                {{firstCol[1]}}
                            </v-btn>
                        </v-card-actions>

                        <v-card-text class="py-0">
                            <v-icon dense class="pr-1">mdi-map-marker</v-icon>
                            {{firstCol[2]}}
                        </v-card-text>

                        <v-card-actions class="py-0">
                            <v-btn text icon href="https://www.instagram.com/foschianos" target="_blank">
                                <v-icon dense class="pr-1">mdi-instagram</v-icon>
                            </v-btn>

                            <v-btn text icon href="https://www.facebook.com/Foschianos" target="_blank">
                                <v-icon dense class="pr-1">mdi-facebook</v-icon>
                            </v-btn>
                        </v-card-actions>
                    </v-card>
                </v-col>

                <v-col cols="2" v-for="(item, index) in colData" :key="index">
                    <v-card tile flat color="transparent">
                        <v-card-title class="text-uppercase pt-0 grey--text title">
                            {{item.title}}
                        </v-card-title>

                        <v-card-actions class="py-0 text-center" v-for="(data, index) in item.items" :key="index">
                            <v-btn text small id="btn-links" :href='data.url'>
                                {{data.name}}
                            </v-btn>
                        </v-card-actions>
                    </v-card>
                </v-col>
            </v-row>

            <v-divider class="mt-10 mb-6"></v-divider>

            <v-row no-gutters justify="end">
                <v-col cols="7">
                    <span class="grey--text text">
                        Copyright © 2020 Construdiseño S.A. El uso de este sitio web implica la aceptación de los Términos y Condiciones y de las Políticas de Privacidad de Construdiseño S.A. Las fotos son a modo ilustrativo. La venta de cualquiera de los productos publicados está sujeta a la verificación de stock. Los precios online para los productos presentados/publicados en www.foschia.com.ar son válidos exclusivamente para la compra vía internet en las páginas antes mencionadas. foschia.com.ar
                    </span>
                </v-col>

                <v-col cols="4">
                    <v-card tile flat color="transparent">
                        <v-card-title class="text-uppercase pt-0 grey--text title">
                            sellos
                        </v-card-title>

                        <v-card-actions class="py-0 text-center">
                            <v-btn text v-for="(item, index) in sellosData" :key="index">
                                <v-img :src='item.title' max-height="50px" :max-width='item.width'/>
                            </v-btn>
                        </v-card-actions>
                    </v-card>
                </v-col>
            </v-row>

            <v-divider class="mt-10 mb-6"></v-divider>

            <v-row no-gutters justify="center" class="pb-5">
                <span class="grey--text text">
                    Diseñado y desarrollado por
                    <v-btn text dense id="btn-drubbit" href="https://drubbit.com/" target="_blank">drubbit.com</v-btn>
                </span>
            </v-row>
        </v-container>
    </v-footer>
</template>


<style>
    .v-card>.v-card__title {
        font-size: .9em !important;
    }

    #btn-links {
        text-transform: none;
        font-weight: 300;
        font-size: .8em ;
    }

    .v-card>.v-card__text, .text {
        font-size: .8em;
    }

    #btn-drubbit {
        text-transform: none;
        padding: 0;
        vertical-align: baseline;
        color: #007AC1;
    }
</style>


<script>
export default {
    name: 'FooterVue',
    data: () => ({
        firstCol: [
            'info@foschia.com.ar',
            '(011) 6012-3758',
            'Colectora Este 30451, El Talar, Buenos Aires'
        ],
        colData: [
            {
                title: "institucional",
                items: [
                    {
                        name: "Sobre Foschia",
                        url: "https://foschia.com.ar/product/griferia-de-cocina-ultragrif-jack-steel-monocomando/bl3JqZclUlXJyohuw7d92w#"
                    },
                    {
                        name: "Sucursales",
                        url: "https://foschia.com.ar/sucursales"
                    },
                    {
                        name: "Información legal",
                        url: "https://foschia.com.ar/terminos-y-condiciones"
                    }
                ]
            },
            {
                title: "servicio al cliente",
                items: [
                    {
                        name: "Políticas de envío",
                        url: "https://foschia.com.ar/politicas-de-envio"
                    },
                    {
                        name: "Políticas de cambio",
                        url: "https://foschia.com.ar/politicas-de-cambio"
                    },
                    {
                        name: "Cláusulas de venta",
                        url: "https://foschia.com.ar/clausulas-de-venta"
                    },
                    {
                        name: "Métodos de pago",
                        url: "https://foschia.com.ar/metodos-de-pago"
                    }
                ]
            },
            {
                title: "tus favoritas",
                items: [
                    {
                        name: "Mejores ofertas",
                        url: "https://foschia.com.ar/ofertas/all"
                    },
                    {
                        name: "Hot Sale",
                        url: "https://foschia.com.ar/hotsale/all"
                    },
                    {
                        name: "Cyber Monday",
                        url: "https://foschia.com.ar/cybermonday"
                    }
                ]
            },
        ],
        sellosData: [
            {
                title: "https://foschia.com.ar/static/img/data-fiscal.webp?x=1607945237",
                width: "36px"
            },
            {
                title: "https://foschia.com.ar/static/img/datos-personales.webp?x=1607945238",
                width: "117px"
            },
            {
                title: "https://foschia.com.ar/static/img/sello-cace.webp?x=1607945342",
                width: "150px"
            },           
        ]
    })
}
</script>