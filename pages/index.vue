<template>
  <section class="container">
    <div>
      <h1 class="title">
        Avaliação de preferência cerebral
      </h1>
      <h2 class="subtitle">
        Em cada uma das 25 questões a seguir, escolha uma das alternativa.
      </h2>
      <div class="links">
        <a
          href="/questionario"
          class="button--yellow">Iniciar</a>
      </div>
      <copy/>
    </div>
  </section>
</template>

<script>
// import AppLogo from '~/components/AppLogo.vue'
import Copy from '~/components/Copy'
export default {
  components: {
    Copy
    //AppLogo
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
  background-color: #f7f7f7;
}

.title {
  font-family: 'Dosis',Arial,Helvetica,Sans-serif;
  display: block;
  font-weight: 300;
  font-size: 4.5rem;
  color: #333;
  margin-bottom: 1rem;
}

.subtitle {
  font-family: 'Dosis',Arial,Helvetica,Sans-serif;
  font-weight: 300;
  font-size: 1.75rem;
  color: #888;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>

