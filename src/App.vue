<template>
  <div class="apex_parent">
    <header class="page_header">
      <span class="header_span">

      </span>
    </header>
    <main class="page_main">
      <section class="section_main">

        <get-joke-button></get-joke-button>

        <display-joke></display-joke>

        <normal-joke-button></normal-joke-button>

        <snake-joke-button></snake-joke-button>

        <loud-joke-button></loud-joke-button>
      </section>
    </main>
    <footer class="page_footer">
     <span class="footer_span">


     </span>
    </footer>
  </div>
</template>

<script>
import DisplayJoke from './components/DisplayJoke.vue';
import GetJokeButton from './components/GetJokeButton.vue';
import NormalJokeButton from './components/NormalJokeButton.vue';
import SnakeJokeButton from './components/SnakeJokeButton.vue';
import LoudJokeButton from './components/LoudJokeButton.vue';

export default {
  name: 'application_jokes',
  components: {

    GetJokeButton,
    DisplayJoke,
    NormalJokeButton,
    SnakeJokeButton,
    LoudJokeButton

  }
}
</script>

<style>

</style>
