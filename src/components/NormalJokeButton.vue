<template>
    <div>


        <button @click="normal_joke_emitter">normal joke</button>


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

            normal_joke_func (joke_holder){


                this.joke = joke_holder;
    

            },



            normal_joke_emitter(){

                  //emitting the joke as joke_selection//

                this.$root.$emit(`joke_selection`, this.joke);


            }

        },


        mounted(){

             //receiving the joke_emit from getjokebutton.vue and calling the respective function//

            this.$root.$on(`joke_emit`, this.normal_joke_func);
        },
    }
</script>

<style scoped>

</style>