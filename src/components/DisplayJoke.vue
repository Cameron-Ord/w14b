<template>
    <div>


        <!--if joke does not equal undefined, displays the joke-->

        <h1 v-if="joke !==undefined">{{ joke }}</h1>

    </div>
</template>

<script>
    export default {


        data() {
            return {
             
                joke: undefined,

            }
        },


        methods:{


            display_joke(joke){

                //making the above joke variable equal the emitted and received joke//

                this.joke = joke;

            }


        },

       
        mounted(){


            //receiving the emitted joke_selection//

            this.$root.$on(`joke_selection`, this.display_joke);
           
        },





    }
</script>

<style scoped>

</style>