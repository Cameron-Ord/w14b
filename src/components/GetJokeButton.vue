<template>
    <div>


    </div>
</template>

<script>
//importing axios//
import axios from 'axios';

    export default {


        //making a variable for the objects//

        data() {
            return {

                joke_holder: {},


            }
        },

        methods:{

            emitJoke(){


                //the function that is called when the API response is successful//

                //if joke_holder is not undefined, globally emits it with 'joke_emit'//
                if(this.joke_holder !== undefined){

                    this.$root.$emit(`joke_emit`, this.joke_holder);

                    //console logging to verify the content of joke_holder//
                    console.log(this.joke_holder);


                }

        
            }


        },

        mounted(){

            //axios request on mount//

            axios({

                method: `GET`,

                url: `https://ron-swanson-quotes.herokuapp.com/v2/quotes`

            }).then((response) => {               

                //if response data is not undefined joke holder will equal reponse[data][0]//

                if(response[`data`] !== undefined){

                    this.joke_holder = response[`data`][0];
                    
                    //calls the emitJoke function when API is successful//
                    this.emitJoke();
                

                }
            
            }).catch((error) => {

                //logs both the error itself and displays an error message when api return is unsuccessful//
                
                console.log(error)
                console.log(`an error has occured`);
              

            });
        },

        
        
    }
</script>



<style scoped>

</style>