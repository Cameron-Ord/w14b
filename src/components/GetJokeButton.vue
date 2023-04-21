<template>
    <div>

    </div>
</template>

<script>

import axios from 'axios';

    export default {


        data() {
            return {
                joke_holder: {}
            }
        },

        mounted(){

            axios({

                method: `GET`,

                url: `https://ron-swanson-quotes.herokuapp.com/v2/quotes`

            }).then((response) => {

                console.log(response);

                

            }).catch((error) => {

                console.log(error);

            });
        }
        
    }
</script>



<style scoped>

</style>