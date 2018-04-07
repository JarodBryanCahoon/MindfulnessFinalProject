<template>
    <v-parallax src="src/images/gap.jpg" height="2000">
        <v-container fluid grid-list-lg>
            <v-layout row wrap>
                <v-flex row-wrap xs4 v-for="cit in citationList">
                    <v-card height = "100%" color="grey">
                        <v-card-title>
                            {{cit.subject}}
                        </v-card-title>
                        <v-card-text>
                            Internet Reference : <a :href=cit.reference>{{cit.reference}}</a>
                        </v-card-text>
                        <v-card-text>
                            {{cit.citation}}
                        </v-card-text>
                    </v-card>
                </v-flex>
            </v-layout>
        </v-container>
    </v-parallax>
</template>

<script>
    import citations from '../data/citations.JSON'
    import VParallax from "vuetify/src/components/VParallax/VParallax";

    export default{
        components: {VParallax},
        data(){
            return{
                citationList : citations
            }
        },

    }
</script>