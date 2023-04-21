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


                this.joke = joke_holder.toUpperCase();

                console.log(this.joke);


            },

            loud_joke_emitter(){

                this.$root.$emit(`joke_selection`, this.joke);


        },

            
        },


        mounted(){

            this.$root.$on(`joke_emit`, this.loud_joke_func);
        }
    }
</script>

<style scoped>

</style>