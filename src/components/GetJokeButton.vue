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

        mounted(){

            axios({

                method: `GET`,

                url: `https://ron-swanson-quotes.herokuapp.com/v2/quotes`

            }).then((response) => {

                console.log(response);


                if(response[`data`] !== undefined){


                    for(let i = 0; i < response[`data`].length; i = i +1){

                    this.joke_holder = response[`data`][i];

                    this.$root.$emit(`joke_emitter`, this.joke_holder);

                    console.log(this.joke_holder.replaceAll(" ", "_"));

                    console.log(this.joke_holder.toUpperCase());

                }

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