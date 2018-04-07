<template>
    <div>
        <v-toolbar>
            <v-menu>
                <v-toolbar-side-icon slot="activator"></v-toolbar-side-icon>
                <v-list>
                    <v-btn>
                        About
                    </v-btn>
                    <v-btn>
                        Gallery
                    </v-btn>
                    <v-btn>
                        Bibliography
                    </v-btn>
                </v-list>
            </v-menu>
            <v-toolbar-title>A Mindful Gallery</v-toolbar-title>
        </v-toolbar>
    </div>
</template>

<script>
    export default {
        data () {
            return {
                currentSite : null,
            }
        }
    }
</script>