<template>
    <div>

        <button @click="normal_joke_emitter">normal_joke</button>



    </div>
</template>

<script>
    export default {
        
        data() {
            return {

                normal_joke:{},

            }
        },



        methods:{

            normal_joke_func (joke_holder){

                this.normal_joke = joke_holder;
    

            },



            normal_joke_emitter(){


                this.$root.$emit(`normal_emitter`, this.normal_joke);
                


            }

        },


        mounted(){

            this.$root.$on(`joke_emitter`, this.normal_joke_func);
        }
    }
</script>

<style scoped>

</style>