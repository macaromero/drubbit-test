<template>
    <v-app-bar color="#007AC1" dark fixed elevation="0" height="78px" class="pl-0">
        <v-btn height="78px" class="pa-0" width="190px" depressed href="https://foschia.com.ar/">
            <v-img src="../assets/logo.png" class="logo pa-0" contain></v-img>
        </v-btn>

        <v-menu open-on-hover offset-y dark nudge-bottom class="hidden-sm-and-down">
            <template v-slot:activator="{ on, attrs }">
                <v-btn v-bind="attrs" v-on="on" elevation="0" text class="font-weight-light text-capitalize hidden-sm-and-down">
                    <v-icon>mdi-chevron-down</v-icon>
                    Menú
                </v-btn>
            </template>

            <v-list id="menu-list">
                <v-list-item v-for="(item, index) in menuItems" :key="index">
                    <v-list-item-title id="menu-item">
                        <v-btn block text class="justify-start text-none">
                            {{item}}
                        </v-btn>
                    </v-list-item-title>
                </v-list-item>
            </v-list>
        </v-menu>
      
        <template>
            <v-form class="form hidden-sm-and-down">
                <v-container>
                    <v-row>
                        <v-col cols="12">
                            <v-text-field append-icon="mdi-magnify" filled placeholder="Buscar productos, marcas y más..." type="text" background-color="white" light full-width class="input" dense></v-text-field>
                        </v-col>
                    </v-row>
                </v-container>
            </v-form>
        </template>

        <template>
            <v-container class="btns-right hidden-sm-and-down pl-0">
                <v-row no-gutters>
                    <v-col cols="6" class="p-0">
                        <v-btn text class="px-0" block href="https://api.whatsapp.com/send?phone=5491160116413" target="_blank">
                            <div class="pa-1">
                                <small class="d-block text-none">
                                    Atención al cliente
                                </small>

                                <span class="font-weight-regular">
                                    <v-icon dense>mdi-whatsapp</v-icon>
                                    11 6011 6413
                                </span>
                            </div>
                        </v-btn>
                    </v-col>

                    <v-col cols="4" class="p-0">
                        <v-btn text class="px-0">
                            <div class="pa-1">
                                <span class="font-weight-regular text-none">
                                    <v-icon dense>mdi-account</v-icon>
                                    Ingresar
                                </span>
                            </div>
                        </v-btn>
                    </v-col>

                    <v-col cols="2" class="p-0">
                        <v-btn text class="px-0">
                            <div class="pa-1">
                                <v-badge color="red" content="0" inline overlap>
                                    <v-icon dense>mdi-cart</v-icon>
                                </v-badge>  
                            </div>
                        </v-btn>
                    </v-col>
                </v-row>
            </v-container>
        </template>
    </v-app-bar>
</template>


<style>
    .logo {
        width: 100%;
    }

    .menu-btn {
        color: white;
    }

    #menu-list {
        background-color: #003a5b;
    }

    #menu-item:hover {
        background-color: rgb(0, 85, 255);
    }

    .form {
        width: 65%;
        height: inherit;
        align-self: baseline;
    }

    .input {
        border-radius: 4px;
    }

    .btns-right {
        width: 30%;
    }
</style>


<script>
    export default  {
        name: 'NavbarVue',
        
        computed: {
            isMobile() {
                return this.$vuetify.breakpoint.xsOnly;
            }
        },
        
        data: () => ({
            menuItems: [
                "Griferías",
                "Pisos",
                "Baño",
                "Cocina",
                "Hogar Y Electrodomésticos",
                "Hábitat",
                "Outlet"
            ]
        })
    }
</script>