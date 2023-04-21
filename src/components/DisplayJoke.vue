<template>
    <div>

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

                this.joke = joke;

            }


        },

       
        mounted(){



            this.$root.$on(`joke_selection`, this.display_joke);
           
        },





    }
</script>

<style scoped>

</style>