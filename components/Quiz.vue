<template>
  <div>
    <table v-show="questionIndex === questionsShuffle.length">
      <tr>
        <th>Águia</th>
        <th>Gato</th>
        <th>Lobo</th>
        <th>Tubarão</th>
      </tr>
      <tr>
        <td>{{ response.i * 4 }}%</td>
        <td>{{ response.c * 4 }}%</td>
        <td>{{ response.o * 4 }}%</td>
        <td>{{ response.a * 4 }}%</td>
      </tr>
    </table>
    <div v-for="(question, index) in questionsShuffle" :key="index">
      <div v-show="index === questionIndex">
        <h2>{{ question.questao }}</h2>
        <ul>
          <li v-for="(alternative, index2) in question.alternativas" :key="index2">
            <a @click.prevent="mark(alternative.perfil)">{{ alternative.alternativa }}</a>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["questoes"],
  data() {
    return {
      questionsShuffle: [],
      questionIndex: 0,
      response: {
        i: 0,
        c: 0,
        o: 0,
        a: 0
      }
    };
  },
  mounted() {
    this.questionsShuffle = this.shuffleArray(this.questoes);
    this.questionsShuffle.forEach((questoes) => {
      this.shuffleArray(questoes.alternativas);
    }); 
  },
  methods: {
    prev() {
      this.questionIndex--;
    },
    next() {
      this.questionIndex++;
    },
    mark(perfil) {
      switch (perfil) {
        case "i":
          this.response.i++;
          break;
        case "c":
          this.response.c++;
          break;
        case "o":
          this.response.o++;
          break;
        case "a":
          this.response.a++;
          break;
      }
      this.next();
    },
    shuffleArray(array) {
      var counter = array.length,
        temp,
        index;
      while (counter > 0) {
        index = Math.floor(Math.random() * counter);

        counter--;

        temp = array[counter];
        array[counter] = array[index];
        array[index] = temp;
      }
      return array;
    }
  }
};
</script>

<style>

</style>
