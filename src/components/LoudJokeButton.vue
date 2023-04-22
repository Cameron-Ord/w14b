<template>
    <div>

        <button @click="loud_joke_emitter">loud joke</button>

    </div>
</template>

<script>
    export default {

         
                data() {
                    return {
                        joke: {},
                    }
                },
      


        methods:{

            loud_joke_func(joke_holder){

                 //making joke = the emitted joke object, but forced to all caps//

                this.joke = joke_holder.toUpperCase();

                console.log(this.joke);


            },

            loud_joke_emitter(){


                  //emitting the altered joke as joke_selection//

                this.$root.$emit(`joke_selection`, this.joke);


        },

            
        },


        mounted(){

            //receiving the joke_emit from getjokebutton.vue and calling the respective function//

            this.$root.$on(`joke_emit`, this.loud_joke_func);
        }
    }
</script>

<style scoped>

</style>