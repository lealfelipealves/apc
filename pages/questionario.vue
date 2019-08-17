<template>
  <section class="container">
    <div>
      <h1 class="title">
        Avaliação de preferência cerebral
      </h1>
      <h2 class="subtitle">
        Em cada uma das 25 questões a seguir, escolha uma alternativa e marque-a no espaço correspondente.
      </h2>
      <div class="links">
        <a
          href="https://nuxtjs.org/"
          target="_blank"
          class="button--green">Iniciar</a>
      </div>

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
      questoes: [],
    };
  },
  mounted() {
    this.loadQuestoes();
  },
  methods: {
    loadQuestoes() {
      this.questoes = data.questoes;
    }
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

