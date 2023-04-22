<template>
    <div>


        <button @click="snake_joke_emitter">snake joke</button>


    </div>
</template>

<script>
export default {
    data() {
        return {


            joke: {},
        }
    },

    methods: {

        snake_joke_func(joke_holder) {


            //making joke = the emitted joke object, with all spaces replaced with _//

                this.joke = joke_holder.replaceAll(` `, `_`);

                console.log(this.joke);



        },

        snake_joke_emitter() {

            //emitting the altered joke as joke_selection//


            this.$root.$emit(`joke_selection`, this.joke);


        },


    },




    mounted() {

         //receiving the joke_emit from getjokebutton.vue and calling the respective function//


        this.$root.$on(`joke_emit`, this.snake_joke_func);
    }

}

</script>

<style scoped></style>