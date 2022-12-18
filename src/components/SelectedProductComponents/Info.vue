<template>
    <v-card class="mx-auto" width="800px" flat>
        <v-container class="pl-6 pb-10">
            <v-row>
                <v-card-text class="pb-2 pt-8">
                    <p class="text--primary mb-0 font-weight-medium" id="title">{{information.title}}</p>
                </v-card-text>
            </v-row>

            <v-row>
                <v-col :cols='information.info.length <= 2 ? "12" : "3"' v-for="(item, index) of information.info" :key="index" class="pb-2">
                    <v-card-text class="pb-0">
                        <div>
                            <p class="text-uppercase mb-0 font-weight-bold" id="item-title">{{item.title}}</p>
                        </div>
                        <p class="mb-0" id="item-desc">{{item.desc}}</p>
                    </v-card-text>
                </v-col>
            </v-row>
        </v-container>
    </v-card>
</template>


<style>
    #title {
        font-size: 1.7em;
    }

    #item-title {
        color: #007AC1;
        font-size: 0.9em;
    }

    #item-desc {
        font-size: 1.1em;
    }
</style>


<script>
    export default {
        name: "InfoVue",
        
        props: ['information']
    }
</script>