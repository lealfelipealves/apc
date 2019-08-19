<template>
  <div>
    
    <div v-for="(question, index) in questionsShuffle" :key="index">
      <div v-show="index === questionIndex">
        <h3 v-show="questionIndex !== questionsShuffle.length">{{questionIndex + 1}} / {{ questionsShuffle.length}}</h3>
        <h2>{{ question.questao }}</h2>
        <ul>
          <li class="notSelectable" v-for="(alternative, index2) in question.alternativas" :key="index2"  @click.prevent="mark(alternative.perfil)">
            {{ alternative.alternativa }}
          </li>
        </ul>
      </div>
    </div>

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
ul {
  list-style: none;
  padding: 0;
}

li {
  background-color: #fff;
  border: 2px solid #e8ebed;
  display: block;
  padding: 15px 15px;
  box-sizing: content-box;
  border-radius: 5px;
  margin-top:1rem;
  cursor: pointer;
}

li:hover {
  border: 2px solid #fc3;
}

.notSelectable {
    -webkit-touch-callout: none;  /* iPhone OS, Safari */
    -webkit-user-select: none;    /* Chrome, Safari 3 */
    -khtml-user-select: none;     /* Safari 2 */
    -moz-user-select: none;       /* Firefox */
    -ms-user-select: none;        /* IE10+ */
    user-select: none;            /* Possível implementação no futuro */
    /* cursor: default; */
}
</style>
