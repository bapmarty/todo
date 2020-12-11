<template>
  <div id="app">
    <section class="container">
      <Header />
      <Todo />
    </section>
    <Footer />
  </div>
</template>

<script>

import Header from './components/Header';
import Todo from './components/Todo';
import Footer from './components/Footer';

export default {
  name: 'App',
  components: {
    Header,
    Todo,
    Footer
  }
}
</script>

<style lang="scss">
  html, body, #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
    margin: 0;
    padding: 0;
    height: 100%;
    background: linear-gradient(to left, #ED4C67, #B53471, #833471, #6F1E51);
  }
  .container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
    margin-top: 75px;
  }
</style>
