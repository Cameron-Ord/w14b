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


                this.joke = joke_holder.replaceAll(` `, `_`);

                console.log(this.joke);



        },

        snake_joke_emitter() {


            this.$root.$emit(`joke_selection`, this.joke);


        },


    },




    mounted() {


        this.$root.$on(`joke_emit`, this.snake_joke_func);
    }

}

</script>

<style scoped></style>