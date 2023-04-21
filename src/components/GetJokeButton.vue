<template>
    <div>


    </div>
</template>

<script>

import axios from 'axios';

    export default {


        data() {
            return {

                joke_holder: {},


            }
        },

        methods:{

            emitJoke(){


                if(this.joke_holder !== undefined){

                    this.$root.$emit(`joke_emit`, this.joke_holder);

                    console.log(this.joke_holder);


                }

        
            }


        },

        mounted(){

            axios({

                method: `GET`,

                url: `https://ron-swanson-quotes.herokuapp.com/v2/quotes`

            }).then((response) => {

                console.log(response);


                if(response[`data`] !== undefined){

                    this.joke_holder = response[`data`][0];
                    
                    this.emitJoke();
                

                }
            
            }).catch((error) => {

                console.log(error);

            });
        },

        
        
    }
</script>



<style scoped>

</style>