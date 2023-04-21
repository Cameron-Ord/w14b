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


                this.$root.$emit(`joke_selection`, this.joke);


            }

        },


        mounted(){

            this.$root.$on(`joke_emit`, this.normal_joke_func);
        },
    }
</script>

<style scoped>

</style>