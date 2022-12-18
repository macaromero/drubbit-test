<template>
    <v-container id="product-container" class="py-0 px-0">
        <v-row class="mx-0 my-0 p-0">
            <v-col cols="8" class="mx-0 px-0 my-0 py-0" id="left-col">
                <ImagesVue/>
                <InfoVue v-bind:information="characteristics"/>
                <InfoVue v-bind:information="extraInfo"/>
            </v-col>

            <v-col cols="4" class="mx-0 px-0 my-0 py-0">
                <SaleCardVue id="right-col"/>
            </v-col>
        </v-row>
    </v-container>
</template>


<style>
    #product-container {
        background-color: white;
    }

    #left-col {
        border-right: 1px solid #eee;
    }

    #right-col {
        position: sticky;
        top: 78px;
    }
</style>


<script>
    import ImagesVue from './SelectedProductComponents/Images.vue';
    import InfoVue from './SelectedProductComponents/Info.vue';
    import SaleCardVue from './SelectedProductComponents/SaleCard.vue';

    export default {
        name: "SelectedProductVue",

        components: {
            ImagesVue,
            InfoVue,
            SaleCardVue
        },

        data () {
            return {
                characteristics: {
                    title: "Características",
                    info: [
                        {
                            title: "tipo de limpieza",
                            desc: "No utilizar abrasivos"
                        },
                        {
                            title: "garantía",
                            desc: "5 años"
                        },
                        {
                            title: "marca",
                            desc: "Ultragrif"
                        },
                        {
                            title: "línea",
                            desc: "Jack"
                        },
                        {
                            title: "con salida",
                            desc: "De mesada"
                        },
                        {
                            title: "cuadro de ducha",
                            desc: "Monocomando"
                        },
                        {
                            title: "tipo de instalación",
                            desc: "Móvil"
                        },
                        {
                            title: "impermeable",
                            desc: "Argentina"
                        },
                    ]
                },
                extraInfo: {
                    title: "Más información",
                    info: [
                        {
                            title: "descripción marca",
                            desc: "ULTRAGRIF es una empresa Argentina con amplia experiencia y trayectoria. dedicada a la comercialización de griferías."
                        },
                        {
                            title: "tipo de pintura",
                            desc: "Apto para calefon y/o termotanque"
                        }
                    ]
                }
            }
        }
    }
</script>