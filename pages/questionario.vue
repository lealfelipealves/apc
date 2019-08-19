<template>
  <section class="container">
    <div>
      <quiz :questoes="questoes" />
    </div>
  </section>
</template>

<script>
import AppLogo from '~/components/AppLogo.vue'
import Quiz from '~/components/Quiz.vue'
import data from '~/assets/json/questoes.json'

export default {
  components: {
    AppLogo,
    Quiz
  },
  data() {
    return {
      questoes: data.questoes
    };
  }
}
</script>

<style>
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  background-color: #f8f8f8;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
  display: block;
  font-weight: 300;
  font-size: 72px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>

