<template>
    <v-parallax src="src/images/mountain2.jpg" height="800">
        <div class="title">
            <h1>About This Project</h1>
        </div>
        <v-container align-center>
            <v-flex width="60%">
                <v-card color="grey">
                    <v-card-text class="paragraphs" v-for="elem in aboutElements">
                        &nbsp&nbsp&nbsp&nbsp {{elem}}
                    </v-card-text>
                </v-card>
            </v-flex>
        </v-container>
    </v-parallax>
</template>

<script>
    import abt from '../data/about.json'

    export default{
        data(){
            return{
                aboutElements : abt
            }
        }
    }
</script>

<style>
    .title{
        margin: 5px;
    }

    h1{
        color: black;
        text-align: center;

    }
    .paragraphs{
        font-size : 2.0em;
    }
</style>