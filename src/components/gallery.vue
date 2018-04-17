<template>
       <v-parallax src="src/images/mountains.jpg" height="800">
              <v-container fluid grid-list-lg>
                     <v-layout row-wrap>
                            <v-flex row-wrap xs4 v-for="image in galleryElements">
                                   <v-card height="100%">
                                          <v-dialog v-model="image.Opened">
                                                 <p>Hell yes</p>
                                          </v-dialog>
                                          <v-layout>
                                                 <v-card-title>
                                                        {{image.Title}}
                                                 </v-card-title>
                                                 <v-btn icon v-on:click.native="image.Opened = true">
                                                        <v-icon>open_with</v-icon>
                                                 </v-btn>
                                          </v-layout>
                                          <v-card-media
                                                 :src=image.ImagePath
                                                 contain
                                          ></v-card-media>
                                   </v-card>
                            </v-flex>
                     </v-layout>
              </v-container>
       </v-parallax>
</template>

<script>
       import gallery from 'src/data/galleryImages.JSON'
       import VDialog from "vuetify/src/components/VDialog/VDialog";
       import VCardMedia from "vuetify/src/components/VCard/VCardMedia";

       export default {
           components: {
               VCardMedia,
               VDialog},
           data(){
               return{
                   galleryElements : gallery
               }
           }
       }
</script>