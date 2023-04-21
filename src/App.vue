<template>
  <div class="apex_parent">
    <header class="page_header">
      <span class="header_span">

      </span>
    </header>
    <main class="page_main">
      <section class="section_main">

        <get-joke-button></get-joke-button>


      </section>
    </main>
    <footer class="page_footer">
     <span class="footer_span">


     </span>
    </footer>
  </div>
</template>

<script>
import GetJokeButton from './components/GetJokeButton.vue';
export default {
  name: 'application_jokes',
  components: {

    GetJokeButton

  }
}
</script>

<style>

</style>
