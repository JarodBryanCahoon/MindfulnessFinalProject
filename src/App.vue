<template>
  <div>
    <NavBar :changePage=changeSite></NavBar>
    <Gallery v-if="this.checkCurrentSite('Gallery')" :getHeight=giveHeight></Gallery>
    <Biblio v-if="this.checkCurrentSite('Biblio')"></Biblio>
    <About v-if="this.checkCurrentSite('About')"></About>
  </div>
</template>

<script>
    import NavBar from './components/navbar.vue'
    import Gallery from './components/gallery.vue'
    import Biblio from './components/bibliography.vue'
    import About from './components/about.vue'

    export default {
        data () {
            return {
                currentSite : 'About',
            }
        },

        components: {
            NavBar,
            Gallery,
            Biblio,
            About
        },

        methods : {
            changeSite(String){
                this.currentSite = String;
            },

            checkCurrentSite(site){
                return this.currentSite == site;
            },

            giveHeight(image){
                return image.naturalHeight;
            }
        }
    }
</script>
