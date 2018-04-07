<template>
    <div>
        <v-toolbar>
            <v-toolbar-title>A Mindful Gallery</v-toolbar-title>
            <v-spacer></v-spacer>
            <v-btn v-on:click.native="changePage('Gallery')">Gallery</v-btn>
            <v-btn v-on:click.native="changePage('About')">About</v-btn>
            <v-btn v-on:click.native="changePage('Biblio')">Bibliography</v-btn>
        </v-toolbar>
    </div>
</template>

<script>
    export default {
        data () {
            return {
                currentSite : null,
            }
        },

        props : [
            'changePage'
        ]
    }
</script>