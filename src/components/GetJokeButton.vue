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

                    console.log(this.joke_holder.replaceAll(" ", "_"));

                    console.log(this.joke_holder.toUpperCase());

                

                } else {

                    console.log(`error`);
                }
            
            }).catch((error) => {

                console.log(error);

            });
        },

        
        
    }
</script>



<style scoped>

</style>