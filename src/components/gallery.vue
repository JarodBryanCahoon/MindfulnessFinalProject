<template>
       <v-parallax src="src/images/mountains.jpg" height="800">
              <v-container fluid grid-list-lg>
                     <v-layout row-wrap>
                            <v-flex row-wrap xs4 v-for="image in galleryElements">
                                   <v-card height="100%" color="grey">
                                          <v-dialog v-model="image.Opened">
                                                 <v-card color="grey">
                                                        <v-card-title primary-title>Example</v-card-title>
                                                        <img src="src/images/ducky.jpg" height="33%" width="33%">
                                                        <v-card-text>Hello, this is an example of what I will be trying to do</v-card-text>
                                                        <v-card-text>More stuff will be going in here but it is kind of a good start</v-card-text>
                                                        <p><a href="www.google.com">Source</a></p>
                                                 </v-card>
                                          </v-dialog>
                                          <v-layout row>
                                                 <v-card-title>
                                                        {{image.Title}}
                                                 </v-card-title>
                                                 <v-spacer></v-spacer>
                                                 <v-btn icon v-on:click.native="image.Opened = true">
                                                        <v-icon>open_with</v-icon>
                                                 </v-btn>
                                          </v-layout>
                                          <v-flex>
                                                 <v-card-media
                                                         :src=image.img
                                                         contain
                                                         height="300"
                                                 ></v-card-media>
                                          </v-flex>
                                   </v-card>
                            </v-flex>
                     </v-layout>
              </v-container>
       </v-parallax>
</template>

<script>
    import gallery from '../data/galleryImages.JSON'
    import VCardMedia from "vuetify/src/components/VCard/VCardMedia";
    import VParallax from "vuetify/src/components/VParallax/VParallax";

    export default {
        components: {
            VCardMedia,
        },
        data(){
            return{
                galleryElements : gallery
            }
        },
        props:[
            'getHeight'
        ]
    }
</script>