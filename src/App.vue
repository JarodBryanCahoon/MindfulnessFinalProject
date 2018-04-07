<template>
  <div>
    <NavBar></NavBar>
    <Gallery v-if="this.currentSite == Gallery"></Gallery>
    <Biblio v-if="this.currentSite == Biblio"></Biblio>
    <About v-if="this.currentSite == About"></About>
  </div>
</template>

<script>
    import NavBar from '../components/navbar'
    import Gallery from '../components/gallery'
    import Biblio from '../components/bibliography'
    import About from '../components/about'

    export default {
        data () {
            return {
                currentSite : About,
            }
        },

        components: {
            NavBar,
            Gallery,
            Biblio,
            About
        },

        methods : {

        }
    }
</script>
