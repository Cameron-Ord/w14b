<template>
    <div>

        <h1>{{ joke }}</h1>

    </div>
</template>

<script>
    export default {


        data() {
            return {
             
                joke:{}

            }
        },


        methods:{

            display_joke_snake(snake_joke){

                this.joke = snake_joke;

            },

            display_joke_loud(loud_joke){

                this.joke = loud_joke;

            },

            display_joke_normal(normal_joke){

                this.joke = normal_joke;

            }



        },

       
        mounted(){


            this.$root.$on(`snake_emitter`, this.display_joke_snake);
            this.$root.$on(`loud_emitter`, this.display_joke_loud);
            this.$root.$on(`normal_emitter`, this.display_joke_normal);
           
        },





    }
</script>

<style scoped>

</style>