<template>
       <v-parallax src="src/images/mountains.jpg" height="150%">
              <div class="title">
                     <h1>Some of the Positive Effects of Meditation/Mindfulness</h1>
              </div>
              <v-container fluid grid-list-lg>
                     <v-layout row wrap>
                            <v-flex row-wrap xs6 v-for="image in galleryElements">
                                   <v-card height="100%" color="grey">
                                          <v-dialog hide-overlay fullscreen v-model="image.Opened">
                                                 <v-card color="grey">
                                                        <v-toolbar dark>
                                                               <v-toolbar-title class="titles" primary-title>{{image.Title}}</v-toolbar-title>
                                                               <v-spacer></v-spacer>
                                                               <v-btn icon v-on:click.native="image.Opened = false">
                                                                      <v-icon>close</v-icon>
                                                               </v-btn>

                                                        </v-toolbar>
                                                        <v-container>
                                                               <v-card-media
                                                                       :src=image.img
                                                                       contain
                                                                       height="500"
                                                               ></v-card-media>
                                                        </v-container>
                                                        <v-flex>
                                                               <v-card-text class="paragraphs" v-for="text in image.descriptions">&nbsp&nbsp&nbsp&nbsp {{text}}</v-card-text>
                                                        </v-flex>
                                                        <v-layout row>
                                                               <v-card-text class="citations">
                                                                      <a :href=image.imgsrc>Image Source</a>
                                                               </v-card-text>
                                                               <v-spacer></v-spacer>
                                                               <v-card-text class="citations">
                                                                      <a :href=image.res>Research</a>
                                                               </v-card-text>
                                                        </v-layout>

                                                 </v-card>
                                          </v-dialog>
                                          <v-toolbar>
                                                 <v-toolbar-title class="titles">
                                                        {{image.Title}}
                                                 </v-toolbar-title>
                                                 <v-spacer></v-spacer>
                                                 <v-btn icon v-on:click.native="image.Opened = true">
                                                        <v-icon>open_with</v-icon>
                                                 </v-btn>
                                          </v-toolbar>
                                          <v-flex>
                                                 <v-card-media
                                                         :src=image.img
                                                         contain
                                                         height="350"
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
        ],

        methods : {
            tabify(text){
                return "&nbsp&nbsp&nbsp&nbsp" + text;
            }

        }

    }
</script>

<style scoped>
       .titles{
              font-size: 2.5em;
       }

       .paragraphs{
              font-size: 2.0em;
              line-height : 1.5;
       }

       .citations{

       }

       v-card-media{
              margin-top : 5px;
       }

       .title{
              padding : 5px;
       }

       h1 {
              text-align: center;
              color : black;
              fontsize : 5.0em;
       }
</style>